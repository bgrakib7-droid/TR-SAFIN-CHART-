# TR SAFIN CHAT

মোবাইল ও ডেস্কটপে ব্যবহারযোগ্য messaging app (PWA)।

## প্রজেক্টের অবস্থা
এই repository-তে এখনো পূর্ণ application source code যোগ করা হয়নি। আগের প্রস্তুত করা source package-এ PWA frontend, Firebase Authentication/Firestore/Storage integration, owner-only admin rules এবং LiveKit token server রয়েছে। সেগুলো যোগ ও configure না করা পর্যন্ত এটি live multi-user app নয়।

## প্রয়োজনীয় সেটআপ
1. Firebase project তৈরি করে Email/Password Authentication, Firestore এবং Storage চালু করুন।
2. `public/firebase-config.js`-এ Firebase Web config ও নিজের UID বসান।
3. `firestore.rules`-এ owner UID বসিয়ে deploy করুন।
4. Audio/video/group call-এর জন্য LiveKit Cloud এবং নিরাপদ token server configure করুন। API secret কখনো browser code-এ রাখবেন না।
5. Firebase Hosting-এ HTTPS দিয়ে deploy করুন; Android Chrome থেকে Install app করা যাবে।

## নিরাপত্তা
- Owner UID ও Firestore rules-এ একই Firebase UID ব্যবহার করতে হবে।
- LiveKit API secret এবং Firebase service-account key কখনো public repository-তে commit করবেন না।
- Admin UI লুকানো যথেষ্ট নয়; server-side rules-ই access control নির্ধারণ করবে।

## সতর্কতা
এটি এখনো সম্পূর্ণ বা deploy-ready app নয়। Firebase/LiveKit credentials এবং hosting setup ছাড়া real-time chat/call কাজ করবে না।