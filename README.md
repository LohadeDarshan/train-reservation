# 🚆 Train Reservation System #

## 📌 Project Overview

The **Train Reservation System** is a Java-based web application designed to automate the process of train ticket booking and management. It allows users to search for trains, check seat availability, book tickets, and view booking history. The system also provides an **Admin module** to manage trains and schedules efficiently.

This project demonstrates real-world implementation of **Java, JDBC, Servlets, JSP, Maven, CI/CD, and Docker** concepts.

---

## 🛠️ Technologies Used

* **Programming Language:** Java
* **Web Technologies:** JSP, Servlets, HTML, CSS
* **Database:** Oracle Database
* **JDBC Driver:** ojdbc8
* **Server:** Apache Tomcat
* **Build Tool:** Maven
* **Version Control:** Git & GitHub
* **CI/CD Tools:** Jenkins, GitHub Actions
* **Containerization:** Docker

---

## 👥 User Roles and Features

### 👤 User Module

* User registration and login
* Search trains between source and destination
* Check seat availability
* Fare enquiry
* Book train tickets
* View booking history
* Update profile and change password

### 👨‍💼 Admin Module

* Admin login
* Add new trains
* Update train details and schedules
* Cancel trains
* View all available trains

---

## 📂 Project Structure

```
train-reservation/
│── src/
│   └── com.shashi
│       ├── beans
│       ├── service
│       ├── servlets
│       └── utility
│
│── WebContent/
│   ├── HTML pages
│   ├── CSS
│   └── WEB-INF/
│
│── Screenshots/
│── Dockerfile
│── Jenkinsfile
│── pom.xml
│── README.md
```

---

## ⚙️ Installation and Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/train-reservation.git
```

---

### 2️⃣ Database Configuration

1. Install Oracle Database
2. Create tables using the SQL scripts provided in `Dummy-Database.md`
3. Update database credentials in `DBUtil.java`

```java
String url = "jdbc:oracle:thin:@localhost:1521:xe";
String username = "your_db_username";
String password = "your_db_password";
```

---

### 3️⃣ Build the Project

```bash
mvn clean install
```

---

### 4️⃣ Deploy on Apache Tomcat

1. Copy the generated `.war` file from `target/`
2. Paste it into `apache-tomcat/webapps/`
3. Start the Tomcat server

---

### 5️⃣ Access the Application

```
http://localhost:8080/train-reservation
```

---

## 🖼️ Screenshots

Screenshots of the application are available in the **Screenshots** folder, including:

* Login Page
* Train Search Page
* Ticket Booking Page
* Admin Dashboard

---

## 🚀 Key Features

* Secure role-based authentication
* Real-time seat availability
* Easy and fast ticket booking
* Admin-controlled train management
* Maven-based build automation
* CI/CD pipeline using Jenkins
* Docker support for containerized deployment

---

## 📌 Future Enhancements

* Online payment gateway integration
* Email and SMS ticket confirmation
* RESTful API implementation
* Responsive UI using modern frameworks

---

## 👨‍💻 Author

**Darshan Lohade**


## 📄 License

This project is created for **learning and educational purposes**.
