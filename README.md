# To-Do CRUD with Firebase Auth and Firebase Database in Next.js

This project demonstrates how to create a simple To-Do application using Next.js, Firebase Authentication, and Firebase Realtime Database. Users can sign up, log in, and perform CRUD (Create, Read, Update, Delete) operations on their to-do items.

## Table of Contents
- [Installation](#installation)
- [Configuration](#configuration)
- [Features](#features)
- [Usage](#usage)
- [Folder Structure](#folder-structure)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/todo-crud-firebase-nextjs.git
    cd todo-crud-firebase-nextjs
    ```

2. **Install dependencies:**
    ```bash
    npm install
    ```

3. **Run the development server:**
    ```bash
    npm run dev
    ```

## Configuration

1. **Set up Firebase:**
    - Go to the [Firebase Console](https://console.firebase.google.com/).
    - Create a new project.
    - Set up Firebase Authentication (Email/Password).
    - Set up Firebase Realtime Database.
    - Obtain your Firebase configuration (API key, Auth domain, Database URL, etc.).

2. **Add Firebase configuration to your project:**
    - Create a `.env.local` file in the root directory.
    - Add your Firebase configuration to the `.env.local` file:
      ```env
      NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key
      NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_auth_domain
      NEXT_PUBLIC_FIREBASE_DATABASE_URL=your_database_url
      NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
      NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_storage_bucket
      NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_messaging_sender_id
      NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
      ```

3. **Initialize Firebase in your project:**
    - Create a `firebase.js` file in the `lib` folder.
    - Add the following code to initialize Firebase:
      ```javascript
      import firebase from 'firebase/app';
      import 'firebase/auth';
      import 'firebase/database';

      const firebaseConfig = {
        apiKey: process.env.NEXT_PUBLIC_FIREBASE_API_KEY,
        authDomain: process.env.NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN,
        databaseURL: process.env.NEXT_PUBLIC_FIREBASE_DATABASE_URL,
        projectId: process.env.NEXT_PUBLIC_FIREBASE_PROJECT_ID,
        storageBucket: process.env.NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET,
        messagingSenderId: process.env.NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID,
        appId: process.env.NEXT_PUBLIC_FIREBASE_APP_ID,
      };

      if (!firebase.apps.length) {
        firebase.initializeApp(firebaseConfig);
      }

      export default firebase;
      ```

## Features

- **Authentication:**
  - User registration
  - User login
  - User logout

- **CRUD Operations on To-Do items:**
  - Create a new to-do item
  - Read all to-do items
  - Update a to-do item
  - Delete a to-do item

## Usage

### Authentication

- **Sign Up:**
  - Users can register with an email and password.

- **Log In:**
  - Registered users can log in with their email and password.

- **Log Out:**
  - Logged-in users can log out.

### To-Do CRUD Operations

- **Create:**
  - Users can add new to-do items.

- **Read:**
  - Users can view their list of to-do items.

- **Update:**
  - Users can edit existing to-do items.

- **Delete:**
  - Users can delete to-do items.



## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for any features, bug fixes, or enhancements.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
