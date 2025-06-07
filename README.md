Camera Equipment Loan System
A simple, powerful, and shared equipment loaning system designed for schools, colleges, or small organizations. Built with HTML, Tailwind CSS, and Google Firebase, this single-page application allows multiple users to track equipment loans, manage inventory status, and view item history in real-time.

Because it's a single HTML file, it can be easily hosted for free on services like GitHub Pages.

Features
Shared, Real-Time Database: All users with the link see the same data, updated instantly.

Comprehensive Loan Management:

Create new loans with student details and due dates.

View all currently loaned-out items.

Detailed Inventory Tracking:

Add new equipment kits with a list of accessories.

View all available equipment.

Track and update the storage location for each item.

Granular Status Control:

Maintenance Mode: Flag individual items or specific accessories for maintenance.

Missing Items: Flag individual items or specific accessories as missing.

Separate lists for "Under Maintenance" and "Missing" items for clear tracking.

Permanent History Log:

Every loan, return, status change, and maintenance action is recorded.

View a complete chronological history for any piece of equipment.

Checklist System:

Use detailed checklists during the loan and return process to ensure all parts of a kit are accounted for.

Secure Deletion: Permanently delete equipment and its entire history with a confirmation step to prevent accidents.

How to Use
This is a single-file web application. To get it working, you need to:

Set up a Google Firebase project.

Paste your unique Firebase configuration into the HTML file.

Host the HTML file on a web server (like GitHub Pages).

Firebase Setup (Crucial Step)
This application will not work without a Firebase backend. Follow these steps to set it up:

Create a Firebase Project:

Go to the Firebase Console.

Click "Add project" and follow the on-screen instructions to create a new project.

Set up Firestore Database:

In your new Firebase project, go to the Firestore Database section from the left-hand menu.

Click "Create database".

Start in production mode. You can change the security rules later.

Choose a location for your database (e.g., us-central).

Set up Authentication:

Go to the Authentication section.

Click "Get started".

Under the "Sign-in method" tab, enable the Anonymous sign-in provider. This is required for the app to work.

Create a Web App in Firebase:

Go to your Project Settings (click the gear icon next to "Project Overview").

Under the "General" tab, scroll down to "Your apps".

Click the web icon (</>) to create a new web app.

Give it a nickname (e.g., "Loan System") and click "Register app".

Get Your Firebase Config:

After registering, Firebase will show you a firebaseConfig object. It looks like this:

const firebaseConfig = {
  apiKey: "AIza...",
  authDomain: "your-project-id.firebaseapp.com",
  projectId: "your-project-id",
  storageBucket: "your-project-id.appspot.com",
  messagingSenderId: "...",
  appId: "1:..."
};

Copy this entire object.

Paste Config into index.html:

Open the camera_loan_system.html file.

Find the <script type="module"> section at the bottom.

Locate the line that says:

const firebaseConfig = JSON.parse(typeof __firebase_config !== 'undefined' ? __firebase_config : '{}');

Replace that entire line with the firebaseConfig object you copied from Firebase. It should now look like this:

const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  // ...and so on
};

Set the App ID:

Find the line directly below the config:

const appId = typeof __app_id !== 'undefined' ? __app_id : 'camera-loan-system-shared';

You can leave this as is, or change 'camera-loan-system-shared' to your own unique ID to ensure your database path is unique.

Hosting on GitHub Pages
Create a new repository on GitHub.

Upload your edited HTML file to the repository. You can rename it to index.html.

In your repository's settings, go to the "Pages" section.

Under "Source," select the branch you want to deploy from (usually main).

Click "Save". GitHub will provide you with a public URL for your application. It may take a few minutes to go live.

Now anyone with the link can access and use your shared equipment loan system.
