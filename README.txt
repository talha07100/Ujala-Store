UJALA STORE — SETUP GUIDE
=========================

Included:
- index.html: public store + admin dashboard
- firestore.rules: product/review access rules
- storage.rules: image upload security rules

IMPORTANT
This is a Firebase-connected website starter. Real Gmail login, online products and image uploads start working only after Firebase setup and hosting. Do not share admin credentials or Firebase private credentials. Firebase web config is designed to be public; security comes from the rules.

ADMIN EMAIL
The single authorized admin is set to:
talhakhan14746@gmail.com

1) Create Firebase project
- Open https://console.firebase.google.com/
- Create a project named Ujala Store.
- Add a Web App and copy its Firebase config.
- In index.html, replace PASTE_API_KEY, PASTE_PROJECT_ID, PASTE_MESSAGING_SENDER_ID and PASTE_APP_ID with the values Firebase gives you. Use the exact storageBucket value Firebase shows (it may end in .firebasestorage.app).

2) Enable Google sign-in
- Firebase Console > Authentication > Get started > Sign-in method > Google > Enable.
- Authentication > Settings > Authorized domains: add the domain where you will host the website.

3) Create database
- Firebase Console > Firestore Database > Create database.
- Open Rules and paste the complete contents of firestore.rules, then Publish.

4) Enable photo storage
- Firebase Console > Storage > Get started.
- Open Storage Rules, paste storage.rules and Publish.
- If Firebase asks you to enable billing or choose a storage plan, follow the current Firebase Console requirements.

5) Run/host
- For local testing, use a local web server (not file://). For example, from this folder run: python -m http.server 8000 and open http://localhost:8000.
- For public access, deploy to Firebase Hosting or another HTTPS host. Add the hosting domain to Firebase Authentication authorized domains.
- You can upload the files through Firebase Hosting CLI or a compatible static hosting service.

6) Test safely
- Sign in with talhakhan14746@gmail.com. Only this email is authorized in the current rules.
- Try adding a product, uploading a photo, editing, deleting, and adding a clearly labelled demo comment.
- Open the public URL in a private/incognito window to verify visitors can see products and reviews but not admin controls.

NOTES
- This starter stores product information and review comments in Firestore and uploaded photos in Firebase Storage.
- Visitors can read published products and reviews. Only the owner email can create/update/delete products and reviews.
- Comments created by the admin are not verified customer reviews. Mark demo/promotional content clearly and publish genuine customer reviews only with appropriate permission.
- For multiple admins or ownership transfer, the Firestore/Storage rules and app authorization logic must be updated together.
- This package is not yet deployed to a live public URL; you must complete the Firebase setup and hosting steps above.
