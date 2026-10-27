BHARATMART STARTER PROJECT — SETUP GUIDE (Hindi)

Is ZIP mein ye files hain:
1. index.html — website ka structure
2. style.css — responsive design
3. app.js — search, category filters, cart, login, seller submission, pending approval UI
4. firebase-config.js — Firebase web configuration
5. firestore.rules — starter Firestore security rules

ZAROORI: Ye BharatMart ka starter project hai, Flipkart ka exact clone nahi. Ismein sample/demo products dikhte hain. Live orders, payments, shipping, returns, product images upload, OTP, coupons aur full order tracking ke liye alag secure backend/integrations chahiye.

STEP 1 — GitHub par files upload karein
- Apne BharatMart GitHub repository mein jayein.
- Purani index.html ko replace karein.
- Is ZIP se index.html, style.css, app.js, firebase-config.js upload karein.
- README-HINDI.txt aur firestore.rules ko website ke root mein rakhna zaroori nahi; rules ko Firebase Console mein paste karna hai.

STEP 2 — Firebase config set karein
- Firebase Console > Project settings (gear icon) > General > Your apps > Web app.
- Firebase config se apiKey aur appId ki asli values copy karein.
- firebase-config.js mein:
  apiKey: "PASTE_YOUR_FIREBASE_API_KEY_HERE"
  appId: "PASTE_YOUR_FIREBASE_APP_ID_HERE"
  in dono placeholder values ko asli values se replace karein.
- Project ID aur baaki values apne Firebase project se match karein. Andaza laga kar API key mat likhein.

STEP 3 — Email/Password login enable karein
- Firebase Console > Authentication > Sign-in method > Email/Password enable karein.

STEP 4 — Admin UID set karein
- Firebase Console > Authentication > Users mein admin account kholein aur UID copy karein.
- Firestore Console > Rules mein firestore.rules ka content paste karne se pehle
  'PASTE_ADMIN_UID_HERE' ko us admin account ke exact UID se replace karein.
- Publish karein.
- Kisi ka email/phone number UID ki jagah na dalein. UID Authentication > Users mein milta hai.

SECURITY NOTE
- Admin UID ko kabhi public chat ya public repo mein share na karein; Firestore rules mein rakhne par bhi rules ka kaam access control hai, lekin production marketplace ke liye custom claims + trusted server/admin SDK behtar hai.
- Rules mein public write access nahi hai. Isliye UID/config galat hua to permission error aa sakta hai.
- Firestore database pehle create hona chahiye.

STEP 5 — Test
- GitHub Pages site kholein; zaroorat ho to refresh karein.
- Demo products bina Firebase ke bhi dikh sakte hain, lekin login, seller submissions aur admin review ke liye config/rules sahi hone chahiye.
- Agar login API key error aaye, firebase-config.js mein apiKey/appId aur Firebase authorized domains check karein.
- Agar Missing or insufficient permissions aaye, admin UID, collection rules, login state aur Firestore database check karein.

LIMITATION
- Starter app ke demo products sirf sample hain; unhe real inventory na samjhein.
- Product approval, seller approval aur real user data ke liye Firebase setup required hai.
