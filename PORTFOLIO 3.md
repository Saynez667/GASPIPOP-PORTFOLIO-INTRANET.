TASK 0
Priorité	User Story
Must Have	As a user, I want to create an account and log in, so that I can access food offers near me.
Must Have	As a merchant, I want to publish a food donation offer with photo, expiration date, and quantity, so that I can easily share my surplus.
Must Have	As a user, I want to search for food offers near my location, so that I can find what’s available nearby.
Must Have	As a user, I want to reserve a food item, so that it’s guaranteed for me until pickup.
Must Have	As a user, I want to get notified when I reserve an item, so that I know it was successful.
Should Have	As a merchant, I want to see my active and past offers, so that I can manage what I give.
Should Have	As a user, I want to see my reservation history, so that I can track what I’ve picked up.
Could Have	As a user, I want to leave feedback on an offer, so that others know if it was useful.
Won’t Have	As a user, I want to rate merchants, so that quality is rewarded. (Hors MVP)

TASK 1
1 The user opens the website (React).
2 They browse nearby offers (request sent to the backend with their location).
3 The backend retrieves offers from the database (PostgreSQL) and returns the data.
4 The user reserves an offer → POST request → validation → saved to the database.
5 The backend sends an email notification to both the merchant and the user (via Mailgun or SMTP).
6 The user can view their active reservations.


React: modern, fast to develop with, and easy to make responsive.
Flask/Django: suitable for a clear REST API and robust for authentication.
PostgreSQL: relational, well-suited for handling reservations and users.
JWT: simple to manage in a stateless server architecture.
Mailgun or SMTP: to avoid a real-time backend at the initial stage.
![porfolio](https://github.com/user-attachments/assets/a9048afd-6dc6-4b95-8943-922a68df52e0)

TASK 2

