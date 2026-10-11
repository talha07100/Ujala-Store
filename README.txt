UJALA STORE — CONFIGURED WEBSITE

The Firebase web config supplied by the owner is already inserted into index.html.

FILES
- index.html: public store + admin panel
- firestore.rules: Firestore access rules
- storage.rules: photo upload rules (Firebase Storage requires Blaze for this project)

IMPORTANT
1. This ZIP must replace the existing index.html in the GitHub repository. Do not upload it as a differently named HTML file.
2. GitHub repository: https://github.com/talha07100/ujala-store
3. Open index.html in the repository, choose the pencil/edit option if available, or use Add file > Upload files to replace index.html. Commit the changes to main.
4. Wait a few minutes and refresh https://talha07100.github.io/ujala-store/ with Ctrl+Shift+R.
5. The yellow "Setup required" banner should disappear if the configured index.html is the one being served.
6. Firebase Authentication > Settings > Authorized domains must include talha07100.github.io.
7. Admin email in the app and Firestore rules: talhakhan14746@gmail.com.
8. Photo upload won't work until Firebase Storage is enabled; the current Firebase project shows Storage requires Blaze billing.
9. Product/review writes require the published Firestore rules and successful Google sign-in.

Security note: Firebase web config is intended for browser apps. Never share your Gmail password or private service-account keys.
