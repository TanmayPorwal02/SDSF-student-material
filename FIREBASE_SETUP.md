# Firebase setup for sign-in and persistent data

This project reuses the Firebase configuration from the original website. Only someone with access to that Firebase project can enable providers, authorise a hosted domain, and configure database/storage rules. Do not put service-account keys or admin secrets in frontend code.

1. Open Firebase Console and select the project referenced in `js/app.js`.
2. Go to **Authentication → Sign-in method** and enable **Email/Password** and **Google**. Configure the Google support email if prompted.
3. Go to **Authentication → Settings → Authorized domains** and add the domain where the website is hosted. For local testing, use the domain shown by your local server.
4. Under **Firestore Database** and **Storage**, ensure security rules allow signed-in users to read/write only the records and files they are authorised to access. Do not make all database contents publicly writable.
5. Run the site through Live Server or an HTTP server rather than opening `index.html` directly.
6. Test: create a test account, sign out, sign in again, refresh, then confirm the session persists. Test file uploads only after the rules have been reviewed.

The website uses Firebase Authentication's `LOCAL` persistence mode. Account credentials are handled by Firebase Authentication; this frontend does not save passwords to local storage. Cloud persistence for folders/files depends on the Firestore and Storage rules for the connected project.
