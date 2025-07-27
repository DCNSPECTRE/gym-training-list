🏋️ Gym Workout Tracker
A sleek, modern, and fully-featured web application designed to help you track your gym progress with ease. Built with React and Firebase, this single-page application is mobile-friendly, fully customizable, and deployable in minutes.

(Feel free to replace this placeholder image with a screenshot of your own app!)

✨ Features
Secure Google Authentication: Quick and secure sign-in using your Google account.

Dynamic Workout Tracking: Log sets, reps, and weights for each exercise and mark them as complete.

Customizable Workout Plans:

Add or remove extra sets on the fly.

Create entirely new workout days.

Add custom exercises to any day.

Persistent Data: All your workout sessions and custom plans are saved securely to your personal cloud database.

Workout History: Review past sessions to see your progress over time, with the ability to delete accidental entries.

Weekly Activity View: A beautiful visual tracker on the main page shows your workout consistency over the last 7 days.

In-App Exercise Guides: Not sure how to perform an exercise? A handy help button provides simple, clear instructions.

Polished & Mobile-First UI: A clean, modern interface built with Tailwind CSS that looks great on any device.

🛠️ Tech Stack
Frontend: React (via UMD scripts for single-file deployment)

Backend & Database: Google Firebase (Authentication & Firestore)

Styling: Tailwind CSS

JavaScript Transpiler: Babel

🚀 Setup & Deployment
This application is designed for simplicity. It's a single index.html file that can be deployed anywhere without a complex build process.

1. Create a Firebase Project
Before you can run the app, you need a free Firebase project to handle your database and authentication.

Go to the Firebase Console and create a new project.

Add a Web App to your project.

Copy the firebaseConfig object that it provides you.

Navigate to the Authentication section, go to the Sign-in method tab, and enable Google as a provider.

Navigate to the Firestore Database section and create a database, starting in test mode.

Go to the Rules tab in Firestore and replace the default rules with:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /user-workouts/{userId}/{document=**} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}

2. Configure the Code
Open the index.html file.

Find the firebaseConfig object at the top of the <script type="text/babel"> tag.

Paste your own firebaseConfig object that you copied from your Firebase project.

3. Deploy
The easiest way to get this live is with a service like Netlify Drop or GitHub Pages.

For Netlify: Simply drag and drop your index.html file onto the Netlify Drop page.

For GitHub Pages: Push the index.html file to a public GitHub repository and enable GitHub Pages in the repository's settings.

🙏 Acknowledgements
This application was developed with the assistance of Google's Gemini, which provided the initial code, feature implementations, and debugging support.
