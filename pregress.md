Of course! Here's a detailed documentation of what we've discussed and planned so far:

---

# iForgot - ID Card & Document Expiry Date Manager

## Overview:

iForgot is designed to help users manage and track the expiry dates of various types of ID cards and documents. By simply scanning or uploading an image of their ID cards or licenses, users can let the app handle the rest. The app will provide timely reminders for document renewals.

## Tools & Technologies:

- **Frontend:** FlutterFlow
- **Backend & Database:** Supabase

## Features:

1. **User Registration & Login:** Users can sign up using their:
   - Name
   - Date of Birth
   - Email Address (with email verification)
   - Phone Number

2. **Scan ID Cards:** Users can scan or upload images of their ID cards/documents.
   
3. **Automatic Expiry Date Extraction:** The app will attempt to extract the expiry date from the scanned image using Optical Character Recognition (OCR).

4. **Set Reminders:** Users can choose from reminder options: a week, a month, or a few days before the expiry date. They will also receive reminders on the expiry day itself.

5. **Notification Methods:** Reminders will be sent through email.

6. **Multiple Cards Support:** Users can add and manage multiple cards and documents.

7. **Supported Card Types:** Government-Issued, Employee, Student, Healthcare, Membership, Visitor, Loyalty Program, Library, Access Control, Travel, Drivers License, Biometric ID, Bank, Passport, and an option to Customize Card Name.

## Database Design:

### Users Table (in `AUTH` schema):

- **id:** Universally unique identifier (UUID) for each user.
- **email:** Email address of the user.
- **password:** Hashed password.
- **phone_number:** Phone number of the user.
- **date_of_birth:** Date of birth of the user.

### Cards Table:

- **card_id (UUID):** A unique identifier for each card.
- **user_id (UUID):** A foreign key linking to the `users` table. This indicates which user the card belongs to.
- **card_type (varchar):** The type of card (e.g., Government-Issued, Student, etc.).
- **expiry_date (date):** The expiration date of the card.
- **card_image (text):** A URL or reference to where the card's image is stored.
- **custom_name (varchar):** An optional field for users who want to give a custom name to their card.

### Reminders Table:

- **reminder_id (UUID):** A unique identifier for each reminder.
- **card_id (UUID):** A foreign key linking to the `cards` table. This indicates which card the reminder is for.
- **reminder_date (date):** The date on which the reminder should be sent.
- **reminder_type (varchar):** The type of reminder (e.g., a week, a month, a few days).

## Steps Taken:

1. **Project Initialization:** Set up a new project in FlutterFlow and initialized a new project in Supabase.

2. **Database Setup:** Extended the `users` table in the `AUTH` schema to include `phone_number` and `date_of_birth`. Created the `cards` and `reminders` tables with the specified columns and data types.

3. **Discussion on Storing Card Images:** Weighed the pros and cons of storing card images. Decided to store the images securely in the `Storage` schema's `buckets` and ensure that only the user who uploaded the image can access it.

---

---

# Next Steps:

## 1. **Design & UI/UX:**
   - **Mockups & Wireframes:** Before diving into development, create detailed mockups and wireframes for each screen of the app. This will give a clear visual representation of the user journey and interface.
   - **Design System:** Establish a design system that includes colors, typography, and UI components to ensure consistency across the app.
   - **User Feedback:** Consider getting feedback on the designs from potential users or stakeholders to ensure the app is intuitive and user-friendly.

## 2. **Frontend Development (FlutterFlow):**
   - **Page Creation:** Develop all the pages/screens as discussed earlier using FlutterFlow.
   - **Component Reusability:** Create reusable components for elements that appear frequently, such as buttons, input fields, and card displays.
   - **Animations & Transitions:** Implement smooth animations and transitions to enhance user experience.

## 3. **Backend Integration:**
   - **API Endpoints:** Set up API endpoints in Supabase for CRUD operations related to users, cards, and reminders.
   - **Authentication:** Implement email-based authentication using Supabase's built-in auth system.
   - **Image Storage:** If storing card images, set up the necessary logic to upload, retrieve, and delete images from the storage buckets in Supabase.

## 4. **Reminder System:**
   - **Reminder Logic:** Develop the logic to send reminders based on user preferences and card expiry dates.
   - **Email Integration:** Integrate an email service (like SendGrid or Mailgun) to send reminder emails to users.

## 5. **Testing:**
   - **Unit Testing:** Write unit tests for critical app functionalities to ensure they work as expected.
   - **Integration Testing:** Test the integration between the frontend and backend to ensure data flows correctly.
   - **User Testing:** Consider a beta release to a small group of users to gather feedback and identify any usability issues.

## 6. **Security:**
   - **Data Encryption:** Ensure sensitive data, especially images of ID cards, are encrypted at rest.
   - **API Security:** Implement measures to prevent unauthorized access to API endpoints.
   - **Data Privacy:** Ensure the app complies with data protection regulations like GDPR or CCPA.

## 7. **Deployment:**
   - **Backend Deployment:** Ensure the Supabase backend is ready for production.
   - **Frontend Deployment:** Prepare the app for deployment to app stores (iOS & Android). This includes setting up store listings, creating app icons, and writing descriptions.

## 8. **Post-Launch:**
   - **Monitoring:** Monitor app usage, performance, and any potential errors.
   - **Feedback Loop:** Establish a system for users to provide feedback, report bugs, or request features.
   - **Updates & Maintenance:** Regularly update the app based on user feedback, bug fixes, or new feature additions.

## 9. **Marketing & Outreach:**
   - **Launch Strategy:** Plan a launch strategy to promote the app and attract initial users.
   - **User Engagement:** Consider strategies to keep users engaged, such as newsletters, promotions, or new feature announcements.

## 10. **Monetization (if applicable):**
   - **Freemium Model:** Offer a free version with basic features and a premium version with advanced features.
   - **Advertisements:** Consider integrating non-intrusive ads for revenue generation.

## 11. **Continuous Improvement:**
   - **Feature Expansion:** Based on user feedback and market demand, consider adding new features or expanding existing ones.
   - **Performance Optimization:** Continuously monitor and optimize the app's performance to ensure a smooth user experience.

---

---

