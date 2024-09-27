# Blood Donation Website Assignment

## Project Overview

This project is about building a **Blood Donation Website** where:

- Users can create accounts as **donors** or **blood seekers**.
- Blood seekers can search for donors by blood type and location.
- Blood seekers can send blood requests to donors.
- Donors will receive email notifications when requests are made.
- Donors can accept or reject requests.
- Blood seekers can leave reviews for donors after receiving blood.

## Tech Stack

### Frontend

- **React** (with TypeScript)
- **Redux** (for state management)
- **React Router** (for navigation)
- **Tailwind CSS** or **Material UI** (for styling)

### Backend

- **Express** (with TypeScript)
- **MongoDB** (as the database)
- **Nodemailer** (for email notifications)
- **JWT** (for authentication)

---

## Tasks

### 1. Setup

- Set up both **frontend** and **backend** environments.
- Use **React** and **Redux** for the frontend.
- Use **Express** with **TypeScript** for the backend.

### 2. Features to Implement

#### **Frontend**

1. **Home Page**:

   - A search form where users can search for blood donors by blood type and location.
   - A list of matching donors should be displayed after the search.

2. **Authentication**:

   - Create a **register** and **login** page for both **donors** and **blood seekers**.
   - Use **JWT** for authentication.
   - Once authenticated, users should be redirected to their dashboard.

3. **Donor Profile**:

   - Each donor should have a profile page showing their details (name, blood type, location).
   - Blood seekers should be able to view this profile and send a blood request.

4. **Blood Request Form**:

   - Blood seekers should be able to request blood from a donor by submitting a form.
   - Once submitted, the donor should receive an email notification.

5. **Donor Notifications**:

   - Donors should receive notifications when a blood request is sent to them.
   - Donors can **accept** or **reject** the request.

6. **Reviews**:
   - After receiving blood, blood seekers should be able to leave a **review** for the donor.

#### **Backend**

1.  Database Design:
    You can use MongoDB with the following collections:

    1. **Users**:


         - name, email, password, role (user or donor), location, reviews, etc.

    2. **Donors**:


         - name, bloodType, location, availability, emailNotifications, reviews, etc.

        3. **Blood Requests**:
         - requesterId, donorId, status (pending, accepted, rejected, fulfilled), location, etc.

        4. **Reviews**:
         - donorId, userId, rating, comments, date.

2.  **User and Donor Models**:

    - Use **MongoDB** to create **User** and **Donor** models.
    - A **User** can be either a **blood seeker** or a **donor**.

3.  **Authentication**:

    - Implement JWT-based authentication for **registering** and **logging in** users.

4.  **Blood Requests**:

    - Create an endpoint for blood seekers to send a **blood request** to a donor.
    - Implement the logic to send an **email notification** to the donor using **Nodemailer**.

5.  **Accept/Reject Request**:
    - Add an endpoint where donors can **accept** or **reject** a blood request.
6.  **Review System**:
    - Add an endpoint where blood seekers can **submit a review** for a donor.

---

## API Endpoints

### Authentication

- POST /register
  Register as a user (donor or seeker).

- POST /login
  Login and return a JWT.

### Donors

- GET /donors?bloodType=A+&location=Dhaka
  Fetch a list of donors by blood type and location.

- POST /request/
  Send a blood request to a specific donor.

### Reviews

- POST /donor/review
  Submit a review for a donor.

### Notifications

- POST /donor/accept
  Donors can accept or reject a blood request.

- Real-Time Notifications:

- Use WebSocket or Socket.io to notify donors in real-time when a blood request is made.
