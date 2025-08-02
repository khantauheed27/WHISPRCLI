# 🟢 WebChatCLI — Firebase-Based Command-Line Chat Interface

WebChatCLI is a terminal-themed, hacker-style real-time chat application inspired by command-line interfaces (CLIs). It allows anonymous or email-based user authentication, real-time messaging, typing indicators, and online status updates — all built entirely using Firebase's free-tier services. Designed to feel like a UNIX terminal for an immersive experience.

---

## 🚀 Live Demo

🔗 https://webchatcli.web.app  
> Replace this with your actual Firebase Hosting URL.

---

## 🎯 Project Overview

| Feature             | Description                                                        |
|---------------------|--------------------------------------------------------------------|
| 👤 User Auth         | Sign up / login via Firebase Authentication                        |
| 💬 Realtime Chat     | Firestore-powered real-time messaging                              |
| 💡 Typing Indicator  | Shows when the other user is typing                                |
| 🔌 Online Status     | Tracks user presence using Firestore                               |
| 🖥️ Terminal UI       | Hacker-friendly UX with CLI aesthetics                             |
| 🌐 Free Hosting      | Hosted on Firebase Hosting (100% free tier)                        |

This project was developed as part of the Cloud Computing Honors Program, demonstrating the use of cloud backend-as-a-service (BaaS) tools like Firebase Authentication, Cloud Firestore, and Firebase Hosting.

---

## 🧠 Technologies Used

- ⚡ HTML, CSS, JavaScript (Vanilla)
- 🔥 Firebase Authentication
- 🔥 Firebase Firestore (Cloud DB)
- 🌐 Firebase Hosting
- 💻 Terminal-inspired UI Design (CLI style)

---

## 📂 Folder Structure
WebChatCLI/
│
├── index.html         # Main application UI + logic
├── style.css          # Hacker-themed styling (optional)
├── script.js          # Firebase + messaging logic
├── README.md          # Documentation file
├── .firebaserc        # Firebase project config
├── firebase.json      # Firebase hosting rules
└── .gitignore         # Node, Firebase & editor ignores

---

## 📚 How It Works

1. **User Signup/Login**: Firebase Authentication is used to register or login a user.
2. **Anonymous Nicknames**: On first signup, a random hacker-style name (e.g., Neo42, Yoda88) is assigned.
3. **User List**: Once logged in, users see all available online/offline users to start chatting.
4. **Real-time Messaging**: Messages are stored and synced via Firestore’s real-time listeners.
5. **Typing Status**: A `typing` collection in Firestore shows live typing indicators.
6. **Online/Offline**: A user’s presence is tracked and updated on page load/unload.

---

## 🔒 Authentication Flow

- Firebase Authentication with Email/Password  
- On signup, user is added to Firestore `users` collection with a generated alias  
- Firestore `users` document stores:

```json
{
  "email": "example@example.com",
  "anonName": "Neo42",
  "online": true
}

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

🏗️ Future Additions (Stretch Goals)
	•	🌐 Deploy to Vercel / Netlify (React version)
	•	🧠 Add GPT-like Auto-Reply Bots
	•	📥 Chat File Uploads
	•	📦 Export Chat Logs to .txt or .json
	•	🔐 Optional Encryption
	•	📱 Mobile UI Enhancements
	•	🌍 Geolocation presence tracking
	•	📊 Realtime usage analytics via Firebase

npm install -g firebase-tools   # Install Firebase CLI
firebase login                  # Log in with Google
firebase init                   # Select Hosting, set public directory to your project root
firebase deploy                 # Deploy to Firebase Hosting

📜 License

This project is licensed under the MIT License

👤 Developed By

Tauheed Abdullah Khan
🎓 Final Year Student — B.Tech in AI & Data Science
🏫 MIT, Aurangabad

