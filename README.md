# Contents
- [Project Overview](#Project-Overview)
- [Project Directory Structure](#Project-Directory-Structure)
- [Team Collaboration Strategy](#Team-Collaboration-Strategy)

---


# Project Overview

This project aims to develop a web application "Create Your Resume" that allows users to create personal resumes using various templates. The application comprises three main components:

1. **Frontend Web Pages (Client-Side)**
2. **Client Backend Scripts**
3. **Server and Database**

---

## 1. Frontend Web Pages

The website consists of several pages, all sharing a common header and footer:

- **Index Page**
- **Login/Register Page**
- **User Resume Page**
- **Resume Templates Page**
- **Resume Edit Page**
- **About Page** *(Optional)*
- **Feedback Page** *(Optional)*
- **Subscription Page** *(Optional)*
- **Admin Page**

### Common Elements

- **Header**: A navigation bar containing hyperlinks to all pages.
    - If the user is **logged in**:
        - The "Login/Register" link changes to "Logout".
        - The username is displayed in the navigation bar.
- **Footer**: Consistent across all pages.
- **Feedback Icon**: Present on every page, linking to the feedback form.

### Page Descriptions

1. **Index Page**:
    - Introduces the benefits of using the web application to create a personal resume.
    - Features a "Get Started" button at the center.
        - **If not logged in**: Redirects to the Login/Register page.
        - **If logged in**: Redirects to the User Resume page.

2. **Login/Register Page**:
    - Standard login and registration functionality with necessary validations.
    - Allows users to switch between login and registration forms.
    - Upon successful login/registration, redirects to the User Resume page.
    - Data interactions are handled via API calls to the server.

3. **User Resume Page**:
    - Displays all resumes created by the user.
    - Includes an "Add" option to create a new resume.
        - Clicking "Add" redirects to the Resume Templates page.
    - Clicking an existing resume opens it in the Resume Edit page.

4. **Resume Templates Page**:
    - Lists all resume templates as thumbnails.
    - Hovering over a thumbnail enlarges it at the center of the page.
    - Clicking a thumbnail opens it in the Resume Edit page.

5. **Resume Edit Page**:
    - Split into two sections:
        - **Left Side**: Input fields for user details (e.g., name, major, experience).
            - Includes a "Save" button.
        - **Right Side**: Displays the selected template with the input data.
    - After clicking "Save", the right side updates to reflect the entered information.
    - *(Optional)* Integrate ChatGPT to analyze user input.

6. **About Page** *(Optional)*:
    - Provides information about the project and team members.

7. **Feedback Page** *(Optional)*:
    - Allows users to submit feedback via email.
    - Preferably accessible through a feedback icon on every page.

8. **Subscription Page** *(Optional)*:
    - Enables users to make payments for subscriptions.

9. **Admin Page**:
    - Accessible only to administrators.
    - Allows admins to search for users and set the number of resumes a user can create.
    - Admins cannot create resumes themselves.

---

## 2. Client Backend Scripts

### Naming Conventions

- **CSS and JavaScript**:
    - Prefix all class names, IDs, and function names with personal initials to prevent naming conflicts during code merges.

### Functionality

1. **Login/Register Page**:
    - Implement necessary input validations.
    - Interact with the server using API calls for data retrieval and storage.

2. **Data Operations (CRUD)**:
    - The client sends HTTP requests to the server.
    - Follow RESTful architecture principles.
    - Server-side handles all data operations (Create, Read, Update, Delete).

3. **Integrate ChatGPT into Resume Edit Page** *(Optional)*:
    - Integrate ChatGPT for analyzing user input to enhance the resume content.

---

## 3. Server and Database

### Server

- **Hosting**:
    - Local server setup is acceptable.
    - Bonus points for deploying on a cloud platform.

- **Technologies**:
    - Use **Node.js** and **Express.js** for server-side development.

### Database

- **Database Choice**:
    - **MongoDB** is mandatory for data storage.

---


# Project Directory Structure
Summary: The backend uses MVC to organize its logic and expose it through a RESTful API, while the frontend uses React to handle the UI and communicate with the backend via the API

## project-root/

```bash
project-root/
├── backend/
├── frontend/
├── package.json
├── README.md
└── .gitignore
```

## backend (MVC & REST)

```bash
backend/
├── package.json
├── server.js
├── config/
│   └── db.js
├── controllers/
│   ├── authController.js
│   ├── resumeController.js
│   ├── adminController.js
│   └── feedbackController.js
├── middleware/
│   ├── authMiddleware.js
│   └── errorMiddleware.js
├── models/
│   ├── User.js
│   ├── Resume.js
│   └── Feedback.js
├── routes/
│   ├── authRoutes.js
│   ├── resumeRoutes.js
│   ├── adminRoutes.js
│   └── feedbackRoutes.js
├── utils/
│   └── helpers.js
├── .env
└── .gitignore
```
## frontend (React)

```bash
frontend/
├── package.json
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── index.js
│   ├── App.js
│   ├── components/
│   │   ├── Header.js
│   │   ├── Footer.js
│   │   ├── FeedbackIcon.js
│   │   └── (other reusable components)
│   ├── pages/
│   │   ├── HomePage.js
│   │   ├── LoginPage.js
│   │   ├── RegisterPage.js
│   │   ├── UserResumePage.js
│   │   ├── ResumeTemplatesPage.js
│   │   ├── ResumeEditPage.js
│   │   ├── AboutPage.js
│   │   ├── FeedbackPage.js
│   │   ├── SubscriptionPage.js
│   │   └── AdminPage.js
│   ├── services/
│   │   ├── authService.js
│   │   ├── resumeService.js
│   │   ├── adminService.js
│   │   └── feedbackService.js
│   ├── context/
│   │   ├── AuthContext.js
│   │   └── (other contexts)
│   ├── hooks/
│   │   └── (custom hooks)
│   ├── styles/
│   │   ├── App.css
│   │   └── (other CSS files)
│   ├── assets/
│   │   ├── images/
│   │   │   └── feedback_icon.png
│   │   └── (other assets)
│   └── utils/
│       └── helpers.js
├── .env
└── .gitignore
```

# Team Collaboration Strategy
My idea is to divide the work by pages.
Since we are 4-person team, here's ChatGPT suggestion:

## Team Roles

### Frontend Developers (2 members)

#### **Frontend Developer 1**:
- Focus on the core UI components in `components/`.
- Implement common elements like `Header`, `Footer`, and `FeedbackIcon`.
- Work on styling (`styles/`) and ensure responsiveness.

#### **Frontend Developer 2**:
- Focus on page components in `pages/`.
- Set up routing with **React Router**.
- Implement state management using **Context API** or **Redux**.
- Handle form validations and user interactions.

### Backend Developers (2 members)

#### **Backend Developer 1**:
- Set up the server (`server.js`) and middleware.
- Implement authentication and authorization (`authController.js`, `authMiddleware.js`).
- Design the User model (`User.js`).

#### **Backend Developer 2**:
- Develop API endpoints for resumes and feedback.
- Implement `resumeController.js`, `feedbackController.js`.
- Design the Resume and Feedback models (`Resume.js`, `Feedback.js`).
- Set up the admin functionalities.

Actually, the suggestion is not a good work distribution. For example, there's too much work for "Frontend Developer 2".
