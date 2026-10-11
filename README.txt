UJALA STORE - FIXED BUILD

1. GitHub repository mein index.html ko is package wale index.html se replace karein.
2. Commit changes karein aur GitHub Pages deploy hone ka intezar karein.
3. Firebase Authentication > Settings > Authorized domains mein talha07100.github.io hona chahiye.
4. Admin Gmail: talhakhan14746@gmail.com
5. Firestore rules file ko Firebase Firestore Rules mein publish karein.
6. Photo upload Firebase Storage use karta hai. Agar Firebase project Storage ke liye Blaze billing maangta hai, to upload feature tab tak kaam nahi karega jab tak billing/Storage setup na ho. Store ke baqi features is se alag hain.
7. Browser mein hard refresh: Ctrl+Shift+R.

Fix in this build: duplicate renderPublic() declaration removed; duplicate declaration could stop the module JavaScript from running, leaving the setup banner visible and buttons unresponsive.


FINAL RUNTIME FIX:
- Fixed the initialization-order bug that referenced $() before declaring const $.
  This caused a JavaScript ReferenceError before any buttons or Firebase listeners could run.
- Firebase initialization errors are now shown in the setup notice and browser console.
- After uploading this index.html to GitHub, commit the change and hard-refresh the published site with Ctrl+Shift+R.
- Admin Gmail is talhakhan14746@gmail.com. Reviews marked Demo / Promotional must remain clearly labelled and must not be represented as genuine customer reviews.
- Image upload depends on Firebase Storage being enabled and available for this Firebase project. If Firebase requires a billing upgrade, image upload cannot work until that service is enabled or an alternative image host is configured.


MULTI-PHOTO UPDATE:
- Product form accepts multiple photos per product.
- Images larger than 900 KB are resized to a maximum 1800px side and compressed to JPEG in the browser. The previous 5MB hard limit was removed.
- Product detail pages show all saved photos. Existing single-photo products remain supported.
- Compression cannot bypass Firebase Storage plan/billing restrictions. If uploads fail with a Firebase Storage billing/permission error, enable Storage or configure alternative image hosting.


PHOTO UPLOAD + CHECKOUT:
- If Firebase Storage upload fails, photos are compressed and stored as separate Firestore productPhotos documents (each under 520 KB). This requires publishing the included firestore.rules. Firestore still has quotas and is not unlimited photo hosting.
- Buy Now uses Cash on Delivery (COD), asks name/phone/address/quantity, and records an order in Firestore.
- This is not card payment processing. Easypaisa/JazzCash/bank transfer need the seller's actual account details. Online card payments require a merchant gateway and secure server-side verification. Do not collect card details in this static site.


BUG FIX: Declared photoDocs and stopPhotos state variables that were referenced by photo listeners but missing from the app state declaration. That ReferenceError could stop product/photo rendering. Public listener errors now display on the page.
