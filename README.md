# Rate Cloud

Rate Cloud is a web application that lets users explore, share, and review digital services. Whether you're offering solutions or looking for honest feedback, Rate Cloud brings user-powered service discovery to life.

> [!TIP]
> **Test User Credentials**  
> **Email**: `tahmid@engineer.com`  
> **Password**: `Abc@123456`

## Features

* **Authentication** – Firebase-based user login, registration, and password reset
* **Add & Manage Services** – Users can post, update, or delete their own services
* **Review System** – Add, edit, or delete reviews for listed services
* **User Dashboard** – Profile page to view and update personal info
* **Membership Page** – Learn about premium benefits
* **Dark Mode Support** – Toggle between light and dark themes
* **JWT-Protected Backend** – Firebase-issued tokens used to protect routes
* **Responsive Design** – Fully mobile-friendly with Tailwind CSS

## Tech Stack

| Category        | Tools                      |
| --------------- | -------------------------- |
| Frontend        | React, Tailwind CSS        |
| Backend         | Express.js, MongoDB        |
| Auth & Hosting  | Firebase (Auth + Hosting)  |
| Auth Protection | Firebase Admin, JWT        |
| Deployment      | Firebase / Render / Vercel |


## Routing Overview

| Route                  | Description                                 |
| ---------------------- | ------------------------------------------- |
| `/`                    | Home page                                   |
| `/membership`          | Membership info and features                |
| `/login`               | Login page                                  |
| `/register`            | Registration page                           |
| `/forget-password`     | Reset password                              |
| `/my-profile`          | View your profile *(protected)*             |
| `/update-profile`      | Update your profile *(protected)*           |
| `/services`            | Browse all services                         |
| `/add-service`         | Add new service *(protected)*               |
| `/service-details/:id` | View service & reviews *(protected)*        |
| `/my-services`         | Manage your posted services *(protected)*   |
| `/update-service/:id`  | Edit your own service *(protected)*         |
| `/my-reviews`          | Manage your submitted reviews *(protected)* |
| `/*`                   | 404 Not Found page                          |

## Installation & Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/tahmid-sarker/Rate-Cloud.git
   ```

2. **Install dependencies**

   ```bash
   cd Rate-Cloud/client
   npm install

   cd ../server
   npm install
   ```

3. **Setup Environment Variables**

   **Client (`client/.env`)**:

   ```
   VITE_API_KEY=yourFirebaseApiKey
   VITE_AUTH_DOMAIN=yourFirebaseAuthDomain
   VITE_PROJECT_ID=yourFirebaseProjectId
   VITE_STORAGE_BUCKET=yourFirebaseStorageBucket
   VITE_MESSAGING_SENDER_ID=yourFirebaseMessagingSenderId
   VITE_APP_ID=yourFirebaseAppId
   VITE_API_URL=yourBackendApiUrl
   ```

   **Server (`server/.env`)**:

   ```
   DB_USER=yourMongoDBUser
   DB_PASSWORD=yourMongoDBPassword
   ACCESS_TOKEN_SECRET=yourJWTSecretKey
   ```

4. **Run Backend**

   ```bash
   node index.js
   ```

5. **Run Frontend**

   ```bash
   npm run dev
   ```

6. Open [http://localhost:5173](http://localhost:5173) in your browser.

## Project Structure

```
client/
└── src/
    ├── assets/
    ├── components/
    │   ├── layout/
    │   │   ├── Header.jsx
    │   │   ├── Footer.jsx
    │   │   └── MainLayout.jsx
    │   └── shared/
    │       ├── DarkModeToggler.jsx
    │       └── DynamicTitle.jsx
    ├── config/
    │   └── firebase.config.js
    ├── context/
    │   ├── AuthContext.jsx
    │   ├── AuthProvider.jsx
    │   ├── ThemeContext.jsx
    │   └── ThemeProvider.jsx
    ├── hooks/
    │   └── useAuth.jsx
    ├── pages/
    │   ├── Auth/
    │   │   ├── Login.jsx
    │   │   ├── Register.jsx
    │   │   └── ForgetPassword.jsx
    │   ├── Services/
    │   │   ├── Services.jsx
    │   │   ├── AddService.jsx
    │   │   ├── ServiceDetails.jsx
    │   │   ├── MyServices.jsx
    │   │   └── UpdateService.jsx
    │   ├── Profile/
    │   │   ├── MyProfile.jsx
    │   │   └── UpdateProfile.jsx
    │   ├── MyReviews.jsx
    │   ├── Membership.jsx
    │   ├── Home.jsx
    │   └── Error.jsx
    ├── routes/
    │   ├── Router.jsx
    │   └── PrivateRoutes.jsx
    ├── main.jsx
    ├── index.css
    └── index.html

server/
└── index.js
```

## Credits

This project was developed by [Md. Tahmid Sarker Mahi](https://tahmid-sarker.github.io).