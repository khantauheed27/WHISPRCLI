🟢 WhisprCLI — Firebase-Based Command-Line Chat Interface

WhisprCLI is a terminal-themed, hacker-style real-time chat application inspired by command-line interfaces (CLIs). It allows anonymous or email-based user authentication, real-time messaging, typing indicators, and online status updates — all built entirely using Firebase's free-tier services. Designed to feel like a UNIX terminal for an immersive experience.

---

🚀 Live Demo

🔗 https://whisprcli.web.app  
> Replace this link with your actual Firebase Hosting URL.

---

🎯 Project Overview

| Feature        | Description                                                            |
|----------------|------------------------------------------------------------------------|
| 👤 User Auth    | Sign up / login via Firebase Authentication                            |
| 💬 Realtime Chat| Firestore-powered real-time messaging                                  |
| 💡 Typing Indicator | Shows when the other user is typing                              |
| 🔌 Online Status| Tracks user presence using Firestore                                   |
| 🖥️ Terminal UI   | Hacker-friendly UX with CLI aesthetics                                 |
| 🌐 Free Hosting | Hosted on Firebase Hosting (100% free tier)                            |

This project was developed as part of the Cloud Computing Honors Program, demonstrating the use of cloud backend-as-a-service (BaaS) tools like Firebase Authentication, Cloud Firestore, and Firebase Hosting.

---

🧠 Technologies Used

- ⚡ HTML, CSS, JavaScript (Vanilla)
- 🔥 Firebase Authentication
- 🔥 Firebase Firestore (Cloud DB)
- 🌐 Firebase Hosting
- 💻 Terminal-inspired UI Design (CLI style)

---

🧩 Folder Structure

WhisprCLI/
│
├── index.html        # Main application code (UI + Firebase logic)
├── README.md         # This documentation file

---

📚 How It Works

1. User Signup/Login: Firebase Authentication is used to register or login a user.
2. Anonymous Nicknames: On first signup, a random hacker-style name (e.g., Neo42, Yoda88) is assigned.
3. User List: Once logged in, users see all available online/offline users to start chatting.
4. Real-time Messaging: Messages are stored and synced via Firestore’s real-time listeners.
5. Typing Status: A typing collection in Firestore shows live typing indicators.
6. Online/Offline: A user’s presence is tracked and updated on page load/unload.

---

🔒 Authentication Flow

- Firebase Authentication with Email/Password
- On signup, user is added to Firestore `users` collection with a generated alias
- Firestore `users` document stores:

{
  "email": "example@example.com",
  "anonName": "Neo42",
  "online": true
}

---

🔥 Firebase Structure

Firestore DB:
├── users (collection)
│   └── [uid] → { email, anonName, online }
│
├── chats (collection)
│   └── [chatId] (uid_uid)
│       └── messages (subcollection)
│           └── [messageId] → { sender, senderName, text, timestamp }
│
├── typing (collection)
│   └── [chatId] → { [uid]: true/false }

---

🏗️ Future Additions (Stretch Goals)

- 🌐 Deploy to Vercel / Netlify (React version)
- 🧠 Add GPT-like Auto-Reply Bots
- 📥 Chat File Uploads
- 📦 Export Chat Logs to `.txt` or `.json`
- 🔐 Optional Encryption
- 📱 Mobile UI Enhancements
- 🌍 Geolocation presence tracking
- 📊 Realtime usage analytics via Firebase

---

📁 Hosting Instructions (Firebase)

1. Install Firebase CLI:
   npm install -g firebase-tools

2. Login & initialize your Firebase project:
   firebase login
   firebase init

3. Deploy the site:
   firebase deploy

> Make sure to select Hosting and set your `index.html` as the public directory.

---

💡 Cloud Concepts Covered

| Concept                | Implementation in WhisprCLI                                     |
|------------------------|------------------------------------------------------------------|
| BaaS                   | Firebase Authentication + Firestore                             |
| Real-Time Communication| Firestore's real-time listener architecture                     |
| Hosting on Cloud       | Firebase Hosting (static web apps on cloud)                     |
| Presence Detection     | Online/Offline status synced to cloud                           |
| Data Modeling          | Structured NoSQL schema in Firestore                            |
| Cost Efficiency        | Fully operates on Firebase’s free Spark Plan                    |

---

📄 License

This project is licensed under the MIT License.

---

✨ Developed By

Tauheed Abdullah Khan  
🎓 Final Year Student - B.Tech in AI & Data Science  
🏫 MIT 
🔗 GitHub: https://github.com/khantauheed85

> This project is part of the Cloud Computing Honors Curriculum to demonstrate real-world BaaS integration using Firebase.

---

🧠 Special Note for Evaluators

WhisprCLI is not only a fully functional real-time chat application but also an academic demonstration of applying Cloud-first Architecture using modern development stacks, including Firebase. This aligns directly with the learning objectives of Cloud Computing courses — showcasing:

- Cost-effective deployment strategies  
- No-server real-time database synchronization  
- Scalable multi-user interaction handling
