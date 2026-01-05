# Auxilio: A Dual-Sided PHP & MySQL Job Portal Platform

**Auxilio** is a robust, feature-rich **Job Board Application** built using native **PHP** and **MySQL**. This platform facilitates **Talent Acquisition** by providing distinct, secure environments for **Job Seekers (Candidates)** and **Employers (Companies)**, streamlining the recruitment lifecycle from job posting to application management.

## 🚀 Key Features & Functionality

Auxilio is engineered for efficient **dual-sided platform management**, ensuring a seamless experience for all users:

### 👤 Candidate Management
*   **Secure Registration & Authentication:** Dedicated workflow (`candidate_registration.html`) for job seekers.
*   **Job Discovery Dashboard:** Candidates can browse and search available **Job Postings** via the `candidate_dashboard.php`.
*   **Streamlined Application System:** Securely applies to jobs (`apply.php`), linking the candidate, job, and company records using **PHP Prepared Statements** for enhanced security.

### 🏢 Employer/Company Management
*   **Company Registration:** Onboarding for businesses (`company_registraton.html`).
*   **Employer Dashboard:** Comprehensive control panel (`company_dashboard.php`) for managing active listings and viewing application metrics.
*   **Job Posting & CRUD:** Easy submission of new job vacancies using dedicated forms (`com_form.html`).
*   **Data Integrity & Transactional Deletion:** Safe removal of jobs (`delete.php`) utilizing **MySQL Transactions** to ensure associated application data (`connection` table records) is also removed, preventing orphan data.

## 🛠️ Technical Stack & Architecture

This project leverages modern web standards and database practices for reliability and performance.

| Component | Technology | Description | Keywords |
| :--- | :--- | :--- | :--- |
| **Backend** | **PHP** (Procedural) | Core business logic and server-side processing, utilizing the `mysqli` extension. | PHP Development, Backend Logic, Data Processing |
| **Database** | **MySQL** | Relational Database Management System (RDBMS) for persistent data storage. | SQL, Database Management, auxilio Schema |
| **Data Security** | **Prepared Statements** | Used extensively (`apply.php`, `delete.php`) to mitigate SQL injection vulnerabilities. | Security, Parameterized Queries, Data Protection |
| **Frontend** | HTML5, CSS3 | Structure and styling, enhanced with responsive frameworks. | Responsive Design, User Interface (UI) |
| **Libraries** | **Bootstrap 4**, PureCSS, jQuery DataTables | Frontend responsiveness and enhanced data presentation features for dashboards. | Frontend Frameworks, Data Visualization |

### Database Schema Highlights
The platform relies on the `auxilio` database (defined in `auxilio.sql`), featuring key tables:
*   `candidate`: User profiles for job seekers.
*   `company`: Employer profiles and business details.
*   `jobs`: Comprehensive table for job vacancies.
*   `connection`: Critical linking table used for the **Applicant Tracking System (ATS)**, associating `company_id`, `user_id`, and `job_id`.

## ⚙️ Setup and Installation Guide

To deploy the Auxilio platform locally, follow these steps:

1.  **Prerequisites:** Ensure you have a running environment with **PHP** (version 8.0+ recommended) and **MySQL** (via XAMPP, MAMP, or similar server stack).

2.  **Database Configuration:**
    *   Create a database named `auxilio` in your MySQL environment.
    *   Import the provided database schema:
        ```bash
        # Import the SQL file
        mysql -u [your_user] -p auxilio < project/auxilio.sql
        ```

3.  **Connection Setup:**
    *   Update the credentials in `project/config.php` if your database configuration differs from the default (`localhost`, `root`, no password).

4.  **Deployment:**
    *   Place the entire `project/` directory inside your web server's document root (e.g., `htdocs/` for Apache).

5.  **Access:**
    *   Start the server.
    *   Begin using the platform by navigating to the main registration pages:
        *   Candidate Registration: `/project/candidate_registration.html`
        *   Company Registration: `/project/company_registraton.html`