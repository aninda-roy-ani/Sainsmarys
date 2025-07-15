# Sainsmary’s – Smart Retail Operations and Customer Shopping Platform

**Prepared by:** Aninda Roy  
**Date:** July 15, 2025

---

## 📖 Table of Contents

1. [Executive Summary](#1-executive-summary)  
2. [Project Objectives](#2-project-objectives)  
3. [System Users and Access Roles](#3-system-users-and-access-roles)  
4. [Key System Features](#4-key-system-features)  
5. [Technical Overview](#5-technical-overview)  
6. [Benefits](#6-benefits)  
7. [Future Enhancements](#7-future-enhancements)  
8. [Conclusion](#8-conclusion)  
9. [Tech Stack](#9-tech-stack)  
10. [Project Structure](#10-project-structure)

---

## 1. Executive Summary

Sainsmary’s is a full-featured smart retail platform designed to simulate the real-time operations of a modern supermarket, combining the digital convenience of online shopping with the operational complexities of physical retail. The system facilitates everything from item discovery based on precise aisle and shelf locations, to automated online ordering, delivery management, and role-based back-office operations.

The system is divided across five distinct user roles—Customer, Online Manager, Trading Manager, Store Manager, and Admin—each with specific responsibilities and dedicated dashboards. Sainsmary’s handles time-sensitive delivery scheduling, automated stock reductions based on physical in-store sales, age-restricted product compliance using local OCR, and scheduled as well as real-time notifications based on user role and shift.

Technologically, the platform uses Java Spring Boot for backend logic and API services, React.js with Tailwind CSS for an intuitive frontend experience, and MySQL for data persistence. Security is enforced using JWT for authentication, alongside optional social login (OAuth2 via Google and Facebook). Email receipts are sent to customers via Gmail SMTP integration, while in-app notifications keep managers informed throughout the day.

From multithreaded physical sales simulations to live inventory threshold alerts, Sainsmary’s is more than a simple supermarket system—it is an end-to-end operational platform that mirrors the real logistics, customer experience, and staffing requirements of a national retail chain.

## 2. Project Objectives

The project aims to build a comprehensive, modular, and intelligent system that models a real supermarket’s digital and physical workflows. Sainsmary’s is a working replica of a full retail operation, not just an e-commerce website.

It empowers customers by enabling them to find exact product locations using structured mappings like aisle, side, bay, and shelf positions (e.g., 31 R10 C3). Orders placed before 1 PM qualify for same-day delivery, while later orders are scheduled for the next day. Age-restricted items require a government-issued ID, and Tesseract OCR is used to verify age automatically based on date of birth.

Java multithreading simulates real-time in-store purchases every 3 minutes, adjusting inventory levels dynamically and feeding into stock alert systems. Trading Managers are alerted when thresholds are reached. Online Managers manage order verification and ID checks via dashboard updates at 4 AM and 1 PM. Store Managers oversee all operations, assign shifts, control discounts, and generate detailed PDF or CSV reports. Admins retain complete control over the platform.

Sainsmary’s blends user experience, compliance, automation, and operational logic in a single deployable system.

## 3. System Users and Access Roles

- **Customer:** Finds product locations, places online orders, uploads ID for restricted items, and receives email receipts.
- **Online Manager:** Manages online orders, confirms delivery, checks ID via OCR, handles failed transactions.
- **Trading Manager:** Manages aisle locations, monitors low stock, and updates product availability.
- **Store Manager:** Oversees all managers, generates reports, handles shift scheduling and discounts.
- **Admin:** Full access to all roles, permissions, rollback features, and system settings.

## 4. Key System Features

- Precise in-store product mapping: Aisle → Row (L/R) → Bay → Shelf → Position.
- Time-based delivery: Same-day if before 1 PM, otherwise next-day.
- OCR-based age verification for 18+ items using ID photo.
- Java multithreaded simulation of in-store purchases every 3 minutes.
- Low-stock alerts and live dashboard updates for Trading Manager.
- Scheduled order alerts at 4 AM and 1 PM for Online Managers.
- Role-specific reporting: CSV for numeric data, PDF for logs and summaries.
- JWT and OAuth2-based authentication.
- Gmail SMTP-based receipt emails (only to customers).

## 5. Technical Overview

- **Backend:** Spring Boot, Spring Security, JWT, OAuth2  
- **Frontend:** React.js, Tailwind CSS  
- **Database:** MySQL (local)  
- **OCR:** Tesseract (local)  
- **Email:** Gmail SMTP  
- **Multithreading:** Java ScheduledExecutorService  
- **Storage:** Local file system for ID uploads  
- **Reports:** CSV and PDF

## 6. Benefits

Sainsmary’s replicates how real supermarkets operate, with intelligent automation, role-based workflows, and real-time inventory tracking. Features like multithreaded simulations and OCR enforcement reduce human load and improve reliability. Shift-based notifications and modular components make it scalable and portfolio-ready.

## 7. Future Enhancements

Potential improvements include a live React WebSocket dashboard, supplier-side inventory APIs, AI-driven sales forecasting, a loyalty point system, and barcode scanning for mobile check-ins. These would expand functionality and increase operational intelligence.

## 8. Conclusion

Sainsmary’s is a full-scale retail operations platform that showcases practical use of backend systems, automation, and compliance enforcement. With its modular architecture, it stands as a powerful example of how software can streamline retail at scale.

## 9. Tech Stack

- **Backend:** Spring Boot, Spring Security, JWT, OAuth2  
- **Frontend:** React.js, Tailwind CSS  
- **Database:** MySQL  
- **OCR:** Tesseract (local)  
- **Email:** Gmail SMTP  
- **Reporting:** CSV + PDF  
- **Auth:** JWT + Google/Facebook  
- **Multithreading:** ScheduledExecutorService

## 10. Project Structure

```
Sainsmary-s/
├── backend/        # Spring Boot app
│   └── pom.xml
├── frontend/       # React app
│   └── package.json
├── uploads/ids/    # Folder for ID image OCR
├── .gitignore
├── README.md
└── LICENSE
```
