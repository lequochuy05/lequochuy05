<div align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=34&pause=1000&color=4DA6FF&center=true&vCenter=true&width=600&lines=Hi+there%2C+I'm+Le+Quoc+Huy+%F0%9F%91%8B;Backend+Development+%F0%9F%91%8B;FullStack+Development+%F0%9F%91%8B" />
</div>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=4DA6FF&height=100&section=footer" width="100%"/>
</p>

<h3 align="center">
  3rd-year IT Student at Vietnam-Korea University (VKU) 🎓
</h3>

<p align="center">
  <a href="https://www.facebook.com/lqh205">
    <img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white"/>
  </a>
  <a href="https://wuchuy.vercel.app/">
    <img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white"/>
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Backend-Java%20%7C%20Spring%20Boot-blue?style=flat"/>
  <img src="https://img.shields.io/badge/Focus-System%20Design%20%26%20Scalability-success?style=flat"/>
  <img src="https://img.shields.io/badge/Learning-Microservices%20%26%20DevOps-orange?style=flat"/>
</p>

---

<div align="left">
  <img src="https://komarev.com/ghpvc/?username=lequochuy05&label=Profile+Views&color=363636&style=flat&abbreviated=true" alt="Profile views" />
</div>

### 👨‍💻 Philosophy

I am a Backend|Fullstack future development deeply passionate about designing **robust, scalable, and maintainable systems**.</br> My focus extends far beyond writing code that "just works."

- **System-Centric Focus:** I specialize in Java & Spring Boot, prioritizing clean architecture and domain-driven design.
- **Performance Optimization:** Experienced in mitigating bottlenecks, handling concurrency, and modeling database schemas for complex variations (e.g., in F&B systems).
- **Event-Driven Architectures:** Skilled in building real-time flows using WebSockets and designing asynchronous data pipelines.
- **Continuous Learning:** Actively expanding my expertise in Microservices, containerization (Docker), and DevOps practices.

💡 **My Goal:** Not just ship features, but understand why the system is designed this way.

---

### 🛠️ Core Stack & Tools

| **Domain** | **Technologies** |
| :--- | :--- |
| ⚙️ **Core Backend** | <img src="https://img.shields.io/badge/-Java%2021-ED8B00?style=flat-square&logo=openjdk&logoColor=white"/> <img src="https://img.shields.io/badge/-Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white"/> <img src="https://img.shields.io/badge/-Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white"/> |
| 🗄️ **Data & Cache** | <img src="https://img.shields.io/badge/-PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white"/> <img src="https://img.shields.io/badge/-MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/> <img src="https://img.shields.io/badge/-Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/> <img src="https://img.shields.io/badge/-Firebase-DD2C00?style=flat-square&logo=firebase&logoColor=white"/> |
| 🐳 **DevOps & API** | <img src="https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/> <img src="https://img.shields.io/badge/-Git-F05032?style=flat-square&logo=git&logoColor=white"/> <img src="https://img.shields.io/badge/-Maven-C71A36?style=flat-square&logo=apachemaven&logoColor=white"/> <img src="https://img.shields.io/badge/-Postman-FF6C37?style=flat-square&logo=postman&logoColor=white"/> |
| 🌐 **Frontend Basics**| <img src="https://img.shields.io/badge/-React-61DAFB?style=flat-square&logo=react&logoColor=black"/> <img src="https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black"/> <img src="https://img.shields.io/badge/-Tailwind%20CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white"/> |

---

### 🏗️ Engineering Case Studies

#### [QROS — QR Ordering System](https://github.com/lequochuy05/order_by_qr) `In Development`
> A full-stack restaurant operations platform with QR ordering, real-time kitchen workflows, payments, inventory, and analytics.

- **System Context:** Customers scan a table QR code to browse the menu, place orders, and track service status while staff operate tables, kitchen, payments, inventory, vouchers, and reports from the management dashboard.
- **Technical Challenges Solved:**
  - **Real-time Operations:** Built STOMP WebSocket and SockJS flows to synchronize new orders and status changes across customer, kitchen, and management interfaces.
  - **Security & Data Integrity:** Implemented JWT authentication, HTTP-only refresh cookies, role-based access control, PostgreSQL persistence, and Flyway migrations.
  - **Platform Integrations:** Integrated Redis caching, PayOS payments, Cloudinary image storage, Gemini AI recommendations, SMTP, and Prometheus metrics.
- **Tech Stack:** `Java 21` `Spring Boot` `PostgreSQL` `Redis` `WebSocket` `JWT` `React` `Docker`

<details>
<summary>🔍 <b>View System Architecture (Real-time Flow)</b></summary>

```mermaid
sequenceDiagram
    autonumber
    participant C as Customer (Mobile)
    participant B as Spring Boot API
    participant DB as PostgreSQL
    participant A as Admin/Kitchen Dashboard

    Note over C, A: Order Lifecycle & Synchronization
    C->>B: Place Order (POST /api/v1/public/orders)
    B->>B: Validate Request & Business Rules
    B->>DB: Persist Order (Normalized Schema)
    DB-->>B: Confirm Persistence
    B-->>C: 201 Created (Order ID)

    rect rgb(240, 248, 255)
        Note right of B: Real-time Broadcast
        B->>A: WebSocket Message: "NEW_ORDER_EVENT"
        A->>A: Update Reactive State (UI)
        A-->>A: Audio Notification for Kitchen
    end
```

**Key Architectural Decisions:**
- **Why WebSockets?** Enables event-driven order and kitchen updates without requiring clients to continuously poll the backend.
- **Relational Integrity:** PostgreSQL and Flyway keep menu, combo, order, inventory, voucher, and user data consistent as the schema evolves.
- **State Management:** The backend acts as the single source of truth and broadcasts order state transitions to connected interfaces.
</details>

---

#### [Onix — Shoes Shop](https://github.com/lequochuy05/Onix) `Completed`
> An end-to-end sneaker e-commerce platform with a native Android customer app and a Spring Boot web dashboard for administrators.

- **Technical Challenges Solved:**
  - **Mobile Architecture:** Built the Android application with Kotlin, MVVM, XML, and Jetpack Compose for product browsing, cart, wishlist, checkout, and order tracking.
  - **Commerce Integrations:** Used Firebase Realtime Database, Cloudinary, Retrofit, and ZaloPay Sandbox to support data synchronization, media, networking, and payments.
  - **Administration:** Developed a Spring Boot and Thymeleaf dashboard for product, inventory, order, and revenue management.
- **Tech Stack:** `Kotlin` `Android SDK` `Jetpack Compose` `MVVM` `Java` `Spring Boot` `Firebase Realtime Database`

---

#### [Hotel Management System](https://github.com/lequochuy05/HotelManagement) `Completed`
> A responsive hotel booking and administration system for managing rooms, reservations, facilities, guests, reviews, and invoices.

- **Technical Challenges Solved:**
  - **Booking Workflow:** Implemented room availability filtering, reservation management, booking status tracking, and customer reviews.
  - **Administration:** Built a dedicated admin panel for rooms, facilities, bookings, user queries, reviews, and PDF records.
  - **Authentication & Notifications:** Added separate customer and administrator authentication flows with SendGrid email support.
- **Tech Stack:** `PHP 8` `MySQL` `JavaScript` `Bootstrap` `HTML/CSS`

---

### 📊 GitHub Analytics

<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=lequochuy05&theme=radical&hide_border=true" />
</p>

<p align="center">
    <img src="https://github-readme-stats.vercel.app/api?username=lequochuy05&show_icons=true&theme=radical&hide_border=true"/>
  </p>

<details>
  <summary><b>👉 Click to view my Languges</b></summary>
  <br/>
  <p align="center">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=lequochuy05&layout=compact&theme=radical&hide_border=true"/>
  </p>
</details>

<details>
  <summary><b>👉 Click to view my Trophies</b></summary>
  <br/>
<p align="center">
  <img src="https://github-trophies.vercel.app/?username=lequochuy05&theme=radical&row=1&column=7&no-frame=true&no-bg=true" alt="Trophies" />
</p>
</details>

---

### 📬 Contact Me
## 🤝 Let's Build Something Together
I am looking for a **Backend|Fullstack internship** opportunity to contribute to a real-world system and learn from senior engineers.

📧 wuchuy05.dev@gmail.com </br>
Available from: [June 2026]

---

## 🐍 My Snake
![Snake animation](https://raw.githubusercontent.com/lequochuy05/lequochuy05/output/github-snake.svg)
