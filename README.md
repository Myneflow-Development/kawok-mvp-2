\# KAWOK WEB APP

\#### Video Demo: https://youtu.be/VrtT7RFRn4E

\#### Description:

Kawok is a web app that connects artists and venues in the music industry. Artists can discover new venues to play there and Kawok is a web application designed to connect artists with venues in the music industry. The goal is to provide a simple platform where:

Artists can discover new venues, showcase their profile, and send requests to perform.

Venues can browse through artists, review their profiles, and accept or decline performance requests.

The app creates a two-sided marketplace for the cultural scene, encouraging artistic expression while also helping venues find the right talent to enrich their events.

⚙️ Architecture

The architecture of the project follows a classic full-stack MVC style:

Backend:

Built with Flask (Python microframework).

The main logic lives in app.py, where different routes are defined (/register, /login, /home, /venues, etc.).

Each route handles request/response cycles and interacts with the database.

Sessions are used to manage authentication and temporary data storage (e.g., multi-step registration).

Database:

Primary DB: PostgreSQL, chosen for its lightweight, efficient, and powerful handling of relational data.

Used to store users (artists and venues), requests, sessions, and application metadata.

During development, MariaDB was used locally for quick testing and validation of SQL queries before connecting to the production PostgreSQL instance.

Frontend:

Built with HTML, CSS, JavaScript, and Bootstrap for UI components.

Uses Jinja2 templating to render dynamic data.

A base file, layout.html, defines the global structure (header, navbar, footer, etc.) which is extended by other templates such as home.html, manage.html, etc.

Pages are modular, making it easier to expand or modify the user experience.

🛠️ Features Implemented
🔑 Authentication & User Management

Registration:

Multi-step registration process.

Partial progress is stored in the session, so users can navigate back without losing data.

Includes full server-side validation to ensure consistency and prevent malicious/garbage data.

Login:

Uses sessions to keep track of authenticated users.

Protects restricted routes to ensure only logged-in users can access certain functionality.

Error Handling:

Integrated helpers.py (adapted from CS50 library).

Displays meaningful error messages and, for fun, shows an “angry cat” image when a layer-8 (user) error occurs.

🖥️ Frontend Functionality

Responsive design powered by Bootstrap components.

Templates divided per feature:

layout.html (global base layout).

home.html (main user dashboard).

manage.html (venue/artist management page).

Other views extend layout.html for consistency.

JavaScript is used to add interactivity, such as form validations, dynamic components, and enhancing the user experience.

🎵 Artist ↔ Venue Interaction

Artists can browse venues and submit requests to perform.

Venues can review artists and accept or decline their requests.

Data stored in PostgreSQL ensures persistent tracking of these interactions.

📂 Code Organization

app.py → Main application logic, route definitions, DB connections.

templates/ → HTML templates using Jinja2.

static/ → CSS, JS, images.

helpers.py → Utility functions (error handlers, session helpers, etc.).

🔒 Security Considerations

Validation happens server-side, not just client-side.

Protects against bypassing JavaScript checks.

Prevents injection or malformed data in the database.

Session-based authentication ensures proper access control.

Use of environment variables (through Flask config) for sensitive values such as DB credentials.

🚀 Development Workflow

Git & GitHub were used for version control.

Branches were created for feature testing and merged after validation.

The commit history reflects iterative development steps: DB setup, Supabase config, deploy fixes, and finalization of MVP.

📌 Future Improvements

Add file uploads (artist media kits, music samples).

Implement messaging system between venues and artists.

Add rating/review system for both sides.

Improve search and filtering for venues and artists.

Containerize the app using Docker for easier deployment.

Expand testing coverage with pytest and automated workflows (CI/CD).

✅ Summary

Kawok combines a Flask backend, PostgreSQL database, and Bootstrap-powered frontend to create a working MVP that connects musicians with venues.
The project demonstrates:

Authentication and session management

Secure registration and login

Artist–venue request workflows

Frontend templating with modular architecture

This MVP is designed as a foundation that can grow into a production-ready platform for real-world cultural events and the music industry ecosystem.
