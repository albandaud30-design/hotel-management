# Cloud-Based Hotel Management System

A comprehensive, full-stack web application designed to streamline hotel operations. This system provides secure administrative control over room inventory, guest profiles, and dynamic booking workflows. Built with a robust Python backend and a responsive, user-friendly frontend interface.

---

## 🛠️ Tech Stack & Architecture

* **Backend Framework:** Python / Flask
* **Database Management:** SQLite via Flask-SQLAlchemy (ORM)
* **Authentication & Security:** Flask-Login (Session Management), Werkzeug (Cryptographic Password Hashing)
* **Frontend UI:** HTML5, CSS3, Bootstrap 5 (Responsive Grid), Jinja2 Templating
* **Architecture Pattern:** Model-View-Controller (MVC) routing principles

---

## 🚀 Core Features

### 1. Secure Administrative Access
* Implementation of `Flask-Login` for protected route management.
* Cryptographic password hashing using `generate_password_hash` to ensure admin credentials are never stored in plaintext.
* Session-based access control preventing unauthorized entry to the dashboard, room, or booking routes.

### 2. Room Inventory Management
* Full CRUD capabilities for hotel rooms.
* Dynamic tracking of room availability, pricing, and room types (e.g., Deluxe, Standard).
* Visual status indicators (Available/Booked) integrated directly into the administrative dashboard.

### 3. Relational Booking Engine
* Relational database schema mapping `Guests` to specific `Rooms` via a central `Booking` model.
* Integrated date-parsing logic to track Check-In and Check-Out schedules.
* Automated availability toggling: booking a room instantly updates its global availability status to prevent double-booking.

### 4. Responsive UI/UX
* Fully responsive web design leveraging Bootstrap 5.
* Clean, non-technical interface utilizing intuitive forms, flash messaging for system feedback, and clear navigation hierarchies.

---

## 🗄️ Database Schema

The system utilizes a relational SQL architecture structured through SQLAlchemy models:
* **`Admin`:** Manages authenticated users (`email`, `password_hash`, `role`).
* **`Room`:** Tracks physical inventory (`number`, `type`, `price`, `available` boolean).
* **`Guest`:** Stores client data (`name`, `email`).
* **`Booking`:** The join table handling reservations, utilizing Foreign Keys (`guest_id`, `room_id`) alongside timestamp data (`check_in`, `check_out`).

---

## ⚙️ Local Setup & Installation

### Prerequisites
* Python 3.8+
* pip (Python Package Installer)

### Installation Steps

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/albandaud30-design/hotel-management.git](https://github.com/albandaud30-design/hotel-management.git)
   cd hotel-management
   # Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
pip install -r requirements.txt
python app.py
source venv/bin/activate
