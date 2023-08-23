---

## 2. **Frontend Development (FlutterFlow):**

### Pages & Their Functionalities:

1. **Welcome Page:**
   - **Functionality:** Display the app's name, a brief description, and options to either sign up or log in.

2. **Signup Page:**
   - **Functionality:** Allow new users to sign up using their name, date of birth, email address, and phone number. After successful registration, redirect to the dashboard.

3. **Login Page:**
   - **Functionality:** Allow returning users to log in using their email and password. Provide a "Forgot Password" option.

4. **Dashboard (Home) Page:**
   - **Functionality:** Display a list of the user's added cards with their expiry dates. Provide options to add a new card or view existing card details.

5. **Add New Card Page:**
   - **Functionality:** Allow users to scan or upload an image of their card, select the card type, and manually input or auto-extract the expiry date. Provide an option for users to give a custom name to their card.

6. **Card Details Page:**
   - **Functionality:** Display detailed information about a specific card, including its image, type, expiry date, and custom name. Provide options to edit or delete the card and set reminders.

7. **Set Reminder Page:**
   - **Functionality:** Allow users to choose a reminder type (e.g., a week, a month, a few days before expiry). Confirm the reminder setting and provide feedback.

8. **Profile Page (optional):**
   - **Functionality:** Display the user's profile information and provide options to edit details or log out.

---

## 3. **Backend Integration:**

- **API Connection:** Connect FlutterFlow to Supabase using the provided API endpoints. This will allow the frontend to communicate with the backend for data storage and retrieval.

- **User Registration & Login:** Integrate the signup and login pages with the `users` table in Supabase. Ensure that passwords are hashed before storage and that email verification is implemented.

- **Card Management:** Integrate the "Add New Card" and "Card Details" pages with the `cards` table in Supabase. Ensure that when a user adds or edits a card, the relevant data is stored or updated in the database.

- **Image Storage:** If storing card images, set up the necessary logic to upload images to the storage buckets in Supabase and retrieve the image URL to store in the `card_image` column of the `cards` table.

- **Reminder Settings:** Integrate the "Set Reminder" page with the `reminders` table in Supabase. Ensure that when a user sets a reminder, the chosen reminder type and date are stored in the database.

---

## 4. **Reminder System:**

- **Reminder Logic:** Develop a backend logic that checks the `reminders` table daily to identify which reminders need to be sent out. The logic should consider the reminder type (e.g., a week, a month, a few days before expiry) and the card's expiry date.

- **Email Integration:** 
   - **Service Selection:** Choose an email service provider (like SendGrid, Mailgun, or another provider) that offers a free tier or fits within the project's budget.
   - **Template Creation:** Design email templates for reminders. The content should be clear and concise, informing the user about the card's expiry date and any necessary actions.
   - **Sending Emails:** Integrate the chosen email service with the backend. When the reminder logic identifies a reminder that needs to be sent, trigger an email to the user using the created template.

- **On-the-Day Reminders:** On the actual expiry date of a card, send a more urgent reminder to the user, informing them that their card/document has expired.

---
