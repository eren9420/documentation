
# User Management Screen Specification

---

#### **Overview:**
This user interface (UI) is designed for managing users in a system. The interface allows administrators to view, add, update, and manage users. Each user has various attributes, such as username, email, phone, roles, and status (enabled/disabled).

---

### **UI Components:**

1. **Table View:**
    - Displays a list of existing users with columns:
      - **ID**: A unique identifier for each user.
      - **User Name**: The username of the user.
      - **Email**: The user's email address.
      - **Enabled**: Indicates if the user is active (true/false).
    - Features:
      - Sortable columns (ascending/descending).
      - Filter option: 'Hide Disabled Users' to only display active users.
      - Buttons for performing actions on the user list (add, edit, delete).

2. **New User Form:**
    - **Username**: Input field for setting the user's login name.
    - **Display Name**: Input field for the name to be displayed.
    - **Phone**: Input field for the user's phone number.
    - **Email**: Input field for the user's email.
    - **User Roles**: Dropdown menu allowing the selection of user roles (Guest, Admin, SuperAdmin).
    - **Enabled**: Toggle for enabling or disabling the user.
    - **Save User Button**: Saves the new user or updates an existing user.

---

### **Requirements:**

1. **User Table:**
    - The table must display all active users by default.
    - Allow users to toggle visibility of disabled users via the 'Hide Disabled Users' checkbox.
    - Columns must be sortable by ID, User Name, Email, and Enabled status.
    - Ensure the 'Enabled' column clearly indicates true/false values.

2. **New User Form:**
    - All input fields must be required except for **Phone**.
    - The **User Roles** dropdown should allow multi-role selection.
    - If an invalid input is provided (e.g., email not valid), display a user-friendly error message near the field.
    - When the **Save User** button is clicked:
      - Validate the form input.
      - Submit data to the backend via an API call.
      - Update the table with the newly added or modified user.
      - Reset the form to its default state after submission.

3. **Interaction & Behavior:**
    - When clicking the **+ New User** button, the form on the right should reset and become active for entering details.
    - If the user is being edited, populate the form fields with the user’s existing data.
    - Upon saving or canceling an action, the form should return to its default state.

4. **Display at Start:**
    - At the beginning, the page should display:
      - The table populated with all users.
      - The **Hide Disabled Users** option unchecked.
      - The **New User** form on the right, empty, and ready for use.
      - Sort users by ID in ascending order by default.

---

### **Technical Requirements:**

- **Responsive Design**: The UI must be responsive and work across various screen sizes.
- **Form Validation**:
  - Validate inputs like email, phone number, and roles before submission.
- **API Integration**: The form and table should interact with a backend API to fetch, add, update, and delete user data.
- **Error Handling**: Provide error messages for form validation failures, API call errors, and connection issues.
- **State Management**:
  - After submitting the form, reset the form state.
  - Ensure changes are reflected in the user table without page refresh.
