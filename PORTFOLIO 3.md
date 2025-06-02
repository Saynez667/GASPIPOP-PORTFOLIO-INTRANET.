TASK 0
Priorité	User Story
- Must Have	As a user, I want to create an account and log in, so that I can access food offers near me.
- Must Have	As a merchant, I want to publish a food donation offer with photo, expiration date, and quantity, so that I can easily share my surplus.
- Must Have	As a user, I want to search for food offers near my location, so that I can find what’s available nearby.
- Must Have	As a user, I want to reserve a food item, so that it’s guaranteed for me until pickup.
- Must Have	As a user, I want to get notified when I reserve an item, so that I know it was successful.
- Should Have	As a merchant, I want to see my active and past offers, so that I can manage what I give.
- Should Have	As a user, I want to see my reservation history, so that I can track what I’ve picked up.
- Could Have	As a user, I want to leave feedback on an offer, so that others know if it was useful.
- Won’t Have	As a user, I want to rate merchants, so that quality is rewarded. (Hors MVP)

TASK 1
-  The user opens the website (React).
- They browse nearby offers (request sent to the backend with their location).
- The backend retrieves offers from the database (PostgreSQL) and returns the data.
- The user reserves an offer → POST request → validation → saved to the database.
- The backend sends an email notification to both the merchant and the user (via Mailgun or SMTP).
- The user can view their active reservations.


React: modern, fast to develop with, and easy to make responsive.
Flask/Django: suitable for a clear REST API and robust for authentication.
PostgreSQL: relational, well-suited for handling reservations and users.
JWT: simple to manage in a stateless server architecture.
Mailgun or SMTP: to avoid a real-time backend at the initial stage.
![porfolio](https://github.com/user-attachments/assets/a9048afd-6dc6-4b95-8943-922a68df52e0)

TASK 2

![task2 drawio](https://github.com/user-attachments/assets/c6ff7087-fb90-457b-be48-7e3ee7ea8cf5)

(PostgreSQL)
User
-----
- id (PK)
- username
- email
- password_hash
- role (enum: 'user', 'merchant')

Merchant  (extends User with 1:1)
-------------------
- user_id (PK, FK User.id)
- shop_name
- address
- phone

Offer
-----
- id (PK)
- merchant_id (FK Merchant.user_id)
- title
- description
- photo_url
- expiration_date (date)
- quantity (int)
- latitude (float)
- longitude (float)
- status (enum: 'available', 'reserved', 'collected', 'expired')

Reservation
-----------
- id (PK)
- offer_id (FK Offer.id)
- user_id (FK User.id)
- reserved_at (timestamp)
- status (enum: 'active', 'cancelled', 'completed')

Notification
------------
- id (PK)
- user_id (FK User.id)
- message (text)
- created_at (timestamp)
- read_status (boolean)
 
React 
- Component	        Description
- LoginForm	        Authentication form
- RegisterForm	    Registration form
- OfferList	        List of nearby offers (with geolocation-based filtering)
- OfferCard	        Card displaying offer details
- OfferForm	        Form to create or edit an offer
- ReservationList	  List of the user's reservations
- NotificationList	List of received notifications
- MapView	          Map showing the location of offers


TASK 3


