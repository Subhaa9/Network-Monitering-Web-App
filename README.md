🌐 Network Monitoring Web App

A web-based network monitoring system that tracks ISP (Internet Service Provider) statuses in real time. It stores network details, downtime history, and provides insights for Airtel, BSNL, Jio, and PGCL connections.


📌 Features

✅ Track ISP Status: Monitor Airtel, BSNL, Jio, PGCL network health.
✅ Database Storage: Logs network IP, bandwidth, status, and downtime duration.
✅ Downtime Logging: Records service provider outages with timestamps.
✅ Real-time Monitoring: Enables network administrators to assess uptime & failures.
✅ Secure API Access: Uses authentication tokens for data access.


🛠️ Database Setup
1️⃣ Create Database

CREATE DATABASE networkiocl;
USE networkiocl;

2️⃣ Create Network Monitoring Table

CREATE TABLE network (
    id INT AUTO_INCREMENT PRIMARY KEY,
    location VARCHAR(255) NOT NULL,
    router_ip VARCHAR(15) NOT NULL,
    airtel_ip VARCHAR(15),
    airtel_bandwidth VARCHAR(10),
    airtel_status ENUM('Up', 'Down') DEFAULT 'Up',
    airtel_status_since DATETIME DEFAULT NULL,
    bsnl_ip VARCHAR(15),
    bsnl_bandwidth VARCHAR(10),
    bsnl_status ENUM('Up', 'Down') DEFAULT 'Up',
    bsnl_status_since DATETIME DEFAULT NULL,
    jio_ip VARCHAR(15),
    jio_bandwidth VARCHAR(10),
    jio_status ENUM('Up', 'Down') DEFAULT 'Up',
    jio_status_since DATETIME DEFAULT NULL,
    pgcil_ip VARCHAR(15),
    pgcil_bandwidth VARCHAR(10),
    pgcil_status ENUM('Up', 'Down') DEFAULT 'Up',
    pgcil_status_since DATETIME DEFAULT NULL,
    token VARCHAR(32) NOT NULL
);

3️⃣ Create Downtime Tracking Table

CREATE TABLE downtime (
    id INT AUTO_INCREMENT PRIMARY KEY,
    service_provider VARCHAR(50) NOT NULL,
    downtime_duration VARCHAR(50) NOT NULL,
    recorded_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

🚀 Installation
1️⃣ Clone the Repository

git clone https://github.com/yourusername/NetworkMonitoringWebApp.git
cd NetworkMonitoringWebApp

2️⃣ Set Up MySQL Database

    Create the database using the SQL scripts above.
    Ensure MySQL is running and update connection settings in your application.

3️⃣ Start the Web Application

Run the backend service or deploy it on a web server.
📡 Usage

    Add network entries with IP addresses, bandwidth, and real-time status.
    Monitor ISP uptime and identify frequent failures.
    View downtime logs to analyze network reliability.


📜 License

This project is MIT licensed. Feel free to use, modify, and contribute.


⭐ Contribute

    Fork this repository
    Create a new feature branch (feature-xyz)
    Submit a Pull Request

📌 If you find this useful, give it a ⭐ on GitHub! 🚀
