# Lab 6: Authentication & Session Management

## Student Information
- **Name:** Phan Tran Anh Quan  
- **Student ID:** ITITIU23019  
- **Class:** Web Application Development G01_lab3 (Tue-1234)

---

## Completed Exercises
- [x] **Exercise 1:** Database & User Model  
- [x] **Exercise 2:** User Model & DAO  
- [x] **Exercise 3:** Login/Logout Controllers  
- [x] **Exercise 4:** Views & Dashboard  
- [x] **Exercise 5:** Authentication Filter  
- [x] **Exercise 6:** Admin Authorization Filter  
- [x] **Exercise 7:** Role-Based UI  
- [x] **Exercise 8:** Change Password  

---

## Authentication Components

### Models
- `User.java`

### DAOs
- `UserDAO.java`

### Controllers
- `LoginController.java`  
- `LogoutController.java`  
- `DashboardController.java`  
- `ChangePasswordController.java`

### Filters
- `AuthFilter.java`  
- `AdminFilter.java`

### Views
- `login.jsp`  
- `dashboard.jsp`  
- `student-list.jsp`  
- `change-password.jsp`

---

## Test Credentials

| Role            | Username | Password     |
|-----------------|----------|--------------|
| **Admin**       | admin    | password123  |
| **Regular User**| john     | password123  |

---

## Features Implemented
- User authentication using **BCrypt**
- **Session management**
- Login/Logout functionality
- Dashboard with statistics
- Authentication filter for protected pages
- Admin authorization filter
- Role-based UI elements
- Password security (Change Password flow)

---

## Security Measures
- BCrypt password hashing  
- Session regeneration after login  
- Session timeout (30 minutes)  
- SQL injection prevention using **PreparedStatement**  
- Input validation  
- XSS prevention (JSTL escaping)

---

## Known Issues
- None

---

## Bonus Features
- None

---

## Time Spent
**Approx. 4 hours**

---

## Testing Notes

### Authentication
- Successfully logged in as both **admin** and **john**
- Invalid credentials and empty fields show correct error messages

### Access Control (Filters)
- Attempting to access protected URLs (e.g., `/dashboard`, `/student`) without authentication redirects to login
- “Back” button after logout does not restore the session (cache disabled)

### Role-Based Authorization
- Logged in as **john** → cannot delete/edit students, blocked by `AdminFilter`
- Logged in as **admin** → has full CRUD access

### Change Password
- Successfully changed the password  
- Verified the old password no longer works  
- Validation errors appear correctly
