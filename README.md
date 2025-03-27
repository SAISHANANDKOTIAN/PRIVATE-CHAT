Private Chat Application
Overview
This is a simple private chat application built using Flask for the backend and HTML, CSS, and JavaScript for the frontend. The application allows users to register, log in, and chat in a shared chatroom. Messages are displayed in real-time, and users can log out when they are done.

The project is designed as a basic chat system where messages are stored in memory rather than a database, making it ideal for learning Flask, handling user sessions, and implementing basic authentication.

Features
✔ User Registration & Login
✔ Simple Authentication System
✔ Shared Chatroom for All Users
✔ Timestamp for Messages (IST Timezone)
✔ Logout Functionality
✔ Styled User Interface

Project Structure
php
Copy
Edit
private-chat-app/
│── static/
│   ├── styles.css        # Styles for the frontend
│   ├── js/chat.js        # JavaScript for real-time interaction (not included in provided code)
│── templates/
│   ├── layout.html       # Base template for the app
│   ├── chat.html         # Chatroom interface
│   ├── login.html        # Login page
│   ├── register.html     # Registration page
│── app.py                # Flask application backend
│── LICENSE               # License file (if added)
│── README.md             # Project documentation
File Descriptions
1. app.py (Backend Application)
This is the main Flask application that handles:

User Authentication: Users can register and log in with a username and password.
Session Management: Keeps track of logged-in users.
Chat Functionality: Users can send messages, which are displayed in real-time with timestamps.
Routing: Manages different pages (login, register, chat, logout).
Key Functions in app.py:

index(): Redirects users to the login page.
login(): Handles user authentication.
register(): Allows new users to sign up.
chat(): Displays the chatroom and allows message posting.
logout(): Logs the user out and ends their session.
2. templates/layout.html (Base Template)
This file defines the HTML structure for all pages. It includes:

A header with the app title.
A content block that gets replaced by specific pages.
A footer with copyright information.
3. templates/chat.html (Chatroom Page)
This is the main chat interface where users can:

View messages from all users.
Send new messages using a form.
Log out using a button.
It loops through existing messages and displays them with a username, message content, and timestamp.

4. templates/login.html (Login Page)
A simple login form where users enter their username and password to access the chatroom. If credentials are incorrect, an error message is displayed.

5. templates/register.html (Registration Page)
A user registration form where new users can create an account. If a username already exists, an error message is shown.

6. static/styles.css (Frontend Styling)
This file styles the chat application using CSS. It includes:

Body Styling: Background color, font styling, and padding.
Chat Container: A clean, modern UI for chat messages.
Form Styling: Input boxes and buttons for login, registration, and chat.
Chat Box Styling: Scrollable chat history with formatted messages.
Design Choices & Considerations
1. Flask & In-Memory Storage
This project does not use a database (e.g., SQLite, MySQL). Instead, it stores users and messages in memory (users = {} and messages = []).
This makes the project simple and easy to understand but means data will be lost when the server restarts.
2. No Real-Time WebSockets
The chat does not use WebSockets (e.g., Socket.IO) for real-time messaging. Instead, messages refresh upon form submission.
This approach keeps the backend simple but does not provide a real-time chat experience.
3. Minimal User Management
Users are stored with plain text passwords (users[username] = password), which is not secure.
Ideally, passwords should be hashed using generate_password_hash() from werkzeug.security.

Future Improvements
✅ Database Integration: Store users and messages persistently.
✅ WebSocket Integration: Enable real-time messaging.
✅ Better Security: Hash passwords and use proper authentication.
✅ User-Specific Chatrooms: Allow private 1-on-1 messaging.
