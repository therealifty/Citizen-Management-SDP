[github_readme (2).md](https://github.com/user-attachments/files/34673556/github_readme.2.md)
# 🏛️ Citizen Management System

A web-based municipal service platform built to digitalize citizen-facing operations such as identity verification, property record-keeping, rental agreement management, property tax collection, and complaint handling. Designed with municipalities like the Chattogram City Corporation in mind, the system replaces fragmented, paper-driven workflows with a single, role-based, and auditable digital portal.

## 📖 Overview

Urban municipalities largely depend on manual procedures for civic services, which are slow, error-prone, and lack transparency. The Citizen Management System addresses this gap by providing citizens with a unified digital channel to register, verify their identity, manage property, pay taxes, and lodge complaints. At the same time, it equips administrators with a centralized dashboard to track requests, tax collections, and complaint resolutions efficiently.

## 🚀 Key Modules & Features

### 🔐 1. Authentication & Role-Based Access Control (RBAC)
* Email-based registration with OTP (One-Time Password) verification via Gmail API.
* Secure cookie-based session authentication.
* Role-based routing separating `Citizen` and `Admin` dashboards.
* Password hashing using ASP.NET Core `IPasswordHasher`.

### 🆔 2. Citizen Verification Module
* NID (National ID) submission with front/back document and passport photo upload.
* Automated cross-checking against a reference `FakeNid` dataset.
* Admin review workflow (Approve/Reject).
* Generation of a verified citizen status and digital certificate.

### 🏠 3. Property Management Module
* Citizens can submit requests to Add, Update, or Transfer properties.
* Administrative approval workflow for all property modifications.
* Search and filter functionality for community properties.
* Auto-generation of the first tax assessment upon property approval.

### 🤝 4. Rent Agreement Module
* Prospective tenants can submit a `RentalRequest` with proposed terms.
* Landlords can counter-propose or accept terms for admin review.
* Auto-generation of a digital `RentAgreement` upon admin approval.
* Property status automatically updates to unavailable when an active agreement is formed.

### 💳 5. Tax Payment Module
* Automated per-fiscal-year `TaxAssessment` generation by administrators.
* Outstanding dues and payment history tracking for citizens.
* Integrated online payment via **Stripe Checkout** (Card).
* Demo payment modes supported for Bank Transfer, bKash, and Nagad.
* Scheduled background jobs to flag overdue assessments.

### 📢 6. Complaint Management Module
* Citizens can file complaints with categories, detailed descriptions, and media attachments (up to 5MB).
* Associated property linking for context.
* Admins can assign handlers, investigate, and resolve or reject complaints.
* Real-time status tracking and official resolution replies for citizens.

## 🏗️ System Architecture

The application follows a robust **Model-View-Controller (MVC)** architectural pattern:
* **View (Presentation):** Razor views (`.cshtml`) with a custom dark-themed CSS design system and Plus Jakarta Sans typography.
* **Controller (Routing & Logic):** 15 ASP.NET Core Controllers handling HTTP requests and authorization.
* **Service (Business Logic):** Reusable services like `TaxAssessmentService`, `StripeCheckoutService`, and `EmailService`.
* **Model (Data Layer):** Entity Framework Core mapping 9 core entities to a relational PostgreSQL database.

## 🛠️ Technology Stack

| Component | Technology Used |
| :--- | :--- |
| **Backend Framework** | ASP.NET Core MVC (C#, .NET 10) |
| **Database** | PostgreSQL (via Entity Framework Core / Npgsql) |
| **Frontend** | Razor Pages, HTML5, Custom CSS, Plus Jakarta Sans |
| **Authentication** | ASP.NET Core Cookie Authentication & RBAC |
| **Payment Gateway** | Stripe.NET (Hosted Checkout & DemoMode) |
| **Email Service** | Gmail API for OTP and Notifications |

## 📑 Project Report

A comprehensive 25-page project report is available for further documentation. It includes detailed system designs, workflow logic, and architectural diagrams.

Included in the report:
- System Requirements Specification (SRS)
- High-Level MVC Architecture Mapping
- Use Case & Sequence Diagrams
- Activity & State Diagrams for all Modules
- Class Collaboration Diagrams (Data Models)
- Implementation Details & Testing Workflows

📥 **[Download Final Report (PDF)](./Citizen_Management_Final_Report_updated%20(1).pdf)

## 🔑 Demo Access

The system automatically seeds demo data on the first run. You can use the following credentials to explore the platform:

* **Admin Login:**
  * Email: `admin@citizen.local`
  * Password: `Admin@123`

* **Citizen Login:**
  * Email: `citizen@citizen.local`
  * Password: `Citizen@123`

## 🔮 Future Enhancements
* Integration with a live National ID (NID) / e-Government registry.
* Production-grade payment implementations with live bKash/Nagad APIs.
* Companion mobile application and SMS notification system.
* Advanced analytics dashboards for revenue forecasting and complaint trend analysis.
* Implementation of versioned EF Core migrations and automated unit testing suites.

## 👥 Team Members

| Name | Student ID | Key Contributions |
| :--- | :--- | :--- |
| **Sazib Hossain** | **0222320005101174** | Authentication, NID Parsing, Tax Integration & Stripe |
| **Mohammad Rayan** | **0222320005101186** | Core Login Logic, Property Registry & Server Deployment |
| **Ifty Anwar** | **0222320005101192** | RBAC Middleware, Ownership Pipelines & Security Audits |
| **Santusti Biswas** | **0222320005101194** | Responsive UI/UX, Document Uploads & Rent Dashboards |

## 🎓 Academic Project Details
* **Course Name:** Software Development Project (CSE 3000)
* **Semester/Batch:** 6th Semester, Section E, 44th Batch (Spring 2026)
* **Department:** Computer Science and Engineering
* **Institution:** Premier University, Chattogram
* **Supervised By:** Rashed Miah (Lecturer, Dept. of CSE)

## ⭐ Support
If you find this municipal management system helpful or interesting, please consider giving it a ⭐ Star!

**Developed by Team Citizen Management**
