# SDSF Academics — DAVV Indore

An independent student-built academic resource portal inspired by the School of Data Science and Forecasting (SDSF), Devi Ahilya Vishwavidyalaya, Indore. It is not the official university website.

## What is included

- Six programme cards; open one programme at a time instead of showing all subjects and PDFs on one long page.
- Programme detail pages with year-wise official academic links and individual subject cards.
- A dedicated folder for every programme/subject combination, each with separate `Notes/` and `Previous-Year-Questions/` folders. Each folder has its own `index.html` preview page and `README.md`.
- PDFs are stored once in `study-materials/previews/` and `study-materials/library/`; each subject folder links to those shared source files so the ZIP stays a manageable size. Download filenames are subject/category-specific.
- Classic university visual theme: warm ivory, forest green, and muted copper; serif headings and restrained transitions rather than a futuristic AI dashboard look.
- Email/password registration and sign-in, Google sign-in, password-reset flow, and persistent Firebase authentication sessions.
- Existing Firebase-backed dashboard/folder/file functionality retained.

## Run locally

1. Extract the ZIP.
2. Open the `sdsf-academics` folder in VS Code.
3. Start it with the Live Server extension, or run `python -m http.server 8000` in this folder and visit `http://localhost:8000`.

## Sign-in and saved accounts

The code uses Firebase Authentication with local session persistence, so signed-in users remain signed in across visits on the same browser. New email/password accounts are created in Firebase Authentication; passwords are not stored in local storage or as plain text. The existing Firebase project configuration is retained from the original project.

For sign-in to work on your hosted website, the Firebase project owner must enable **Email/Password** and **Google** under Firebase Console → Authentication → Sign-in method, add the deployed domain under Authentication → Settings → Authorized domains, and configure Firestore/Storage security rules. Folders/files are saved to Firestore and Firebase Storage only when the project rules permit the operation. If the project is inactive or its providers/rules are disabled, the website cannot override that from frontend code. See `FIREBASE_SETUP.md`.

## Official syllabus links

- Official SDSF academics: https://dsf.dauniv.ac.in/academics.php
- Official SDSF website: https://dsf.dauniv.ac.in/
- DAVV website: https://www.dauniv.ac.in/

The public academic page provides programme resources and current notices, but it does not provide a distinct direct PDF for every course/year combination. Year cards therefore link to the available official course profile or the official Academics page. Check the document title, semester and batch before relying on it.

## Notes about the supplied files

The same supplied files are available under every subject as requested. Renaming only changes the download filename; it does not change the file contents. They have not been verified as actual previous-year examination papers, and some may not match a particular subject.
