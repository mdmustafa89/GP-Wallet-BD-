GP Wallet BD — Netlify + Firebase starter
========================================

ফাইল:
- index.html       ইউজার সাইট
- admin.html       অ্যাডমিন প্যানেল
- app.js           ইউজার লগইন/টাস্ক/আবেদন
- admin.js         অ্যাডমিন কন্ট্রোল
- firebase.js      আপনার দেওয়া Firebase config
- style.css        responsive dark-blue design
- database.rules.json  প্রাথমিক Realtime Database rules

Netlify-তে প্রকাশ:
1. ZIP extract করুন।
2. সব ফাইল একই ফোল্ডারে রাখুন।
3. Netlify-তে Add new site / Deploy manually-তে ফোল্ডার আপলোড করুন।
4. ইউজার লিংক হবে: https://YOUR-SITE.netlify.app/
5. অ্যাডমিন লিংক হবে: https://YOUR-SITE.netlify.app/admin.html
   (Netlify সাবডোমেইন আপনার সাইট তৈরি করার পর নির্ধারিত হবে; আগে থেকে সঠিক লিংক জানা যায় না।)

Firebase সেটআপ:
1. Firebase Console > Authentication > Sign-in method > Email/Password enable করুন।
2. Realtime Database তৈরি করুন।
3. Database Rules-এ database.rules.json-এর নিয়ম বসিয়ে Publish করুন।
4. প্রথমে নিজের অ্যাকাউন্টটি সাইট থেকে তৈরি করুন।
5. Firebase Console > Realtime Database > admins-এ যান।
6. নিজের Firebase Authentication UID-এর অধীনে boolean true যোগ করুন:
   admins
     YOUR_FIREBASE_AUTH_UID: true
   UID Authentication > Users থেকে কপি করতে হবে।
7. এরপর admin.html-এ ওই অ্যাকাউন্ট দিয়ে লগইন করুন।

গুরুত্বপূর্ণ সীমাবদ্ধতা ও নিরাপত্তা:
- এই ফাইলগুলো একটি starter frontend; পূর্ণ উৎপাদন-উপযোগী earning/payment platform নয়।
- ব্যালেন্স ক্রেডিট, ডিপোজিট অনুমোদন, উত্তোলন সম্পন্ন করা ও রেফারেল কমিশন হিসাবের জন্য trusted Cloud Functions/server-side code যোগ করতে হবে। এই starter ইচ্ছাকৃতভাবে অ্যাডমিনের Approve বাটনে সরাসরি ব্যালেন্স যোগ করে না।
- প্রোফাইলের balance field-এ ইউজারের নিজস্ব write অনুমতি production-এ সরাসরি রাখা নিরাপদ নয়। production-এর আগে profiles rules-কে Cloud Functions/সার্ভার দিয়ে balance update করার মতো করে শক্ত করতে হবে।
- স্ক্রিনশট আপলোডের জন্য Firebase Storage rules ও upload UI যোগ করা দরকার; এই starter-এ proof হিসেবে একটি URL দেওয়া হয়।
- Social platform follow/subscribe সব সময় অটো যাচাই করা যায় না। API/বিশ্বস্ত যাচাই না থাকলে manual review করুন।
- 250 BDT verification fee, earning claims, referral, deposit/withdrawal চালু করার আগে আপনার এলাকার আইন, ভোক্তা-সুরক্ষা ও পেমেন্ট প্রদানকারীর শর্ত যাচাই করুন। নিশ্চিত আয়ের প্রতিশ্রুতি দেবেন না।
- Firebase web apiKey সাধারণত client config; তবু Database Rules ও Auth access control অবশ্যই সঠিক রাখুন।
