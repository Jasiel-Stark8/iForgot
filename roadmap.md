# FlutterFlow and Supabase.
### iForgot Product Roadmap:

1. **Project Initialization:**
    - Set up a new project in FlutterFlow.
    - Initialize a new project in Supabase.

2. **Database Design & Setup (Supabase):**
    - **Users Table:** 
        - user_id (Primary Key)
        - name
        - email (Unique)
        - date_of_birth
        - phone_number
        - password (hashed)
    - **Cards Table:**
        - card_id (Primary Key)
        - user_id (Foreign Key)
        - card_type (e.g., Government-Issued, Student, etc.)
        - expiry_date
        - card_image (URL or Blob)
        - custom_name (Optional, for "Customize Your Card Name")
    - **Reminders Table:**
        - reminder_id (Primary Key)
        - card_id (Foreign Key)
        - reminder_date
        - reminder_type (e.g., a week, a month, a few days)

3. **UI/UX Design (FlutterFlow):**
    - Design the app's pages/screens as discussed earlier (Welcome, Signup/Login, Dashboard, Add New Card, etc.).
    - Ensure a user-friendly and intuitive design.

4. **Backend Integration (Supabase & FlutterFlow):**
    - Connect FlutterFlow with Supabase using API endpoints.
    - Implement user registration and email verification.
    - Add functionality to scan/upload cards and store them in the database.
    - Implement the reminder system based on user preferences.

5. **Testing:**
    - Test the app's functionalities to ensure everything works as expected.
    - Ensure data integrity in the database.
    - Test the app on different devices and screen sizes.

6. **Deployment:**
    - Deploy the backend (Supabase) if needed (though Supabase handles most of the deployment aspects).
    - Publish the app to app stores (iOS & Android).

7. **Feedback & Iteration:**
    - Gather feedback from initial users.
    - Make necessary improvements and updates based on feedback.

8. **Maintenance & Updates:**
    - Regularly update the app based on user feedback and any new requirements.
    - Ensure the backend (Supabase) is running smoothly and efficiently.

### Next Steps for Tonight Tuesday AUg 22 2023 -- 01.30 -> 04.00 --:

1. Set up the Supabase project and design the database schema as outlined above.
2. Create the tables (Users, Cards, Reminders) in Supabase.
3. Initialize the project in FlutterFlow and familiarize yourself with its interface.
