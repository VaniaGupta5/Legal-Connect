# LegalConnect – System Design Document

## 1. System Overview

LegalConnect will be implemented as a web application with a modular backend architecture, scalable for future mobile app integration.

---

## 2. Architecture

### 2.1 High-Level Architecture

Frontend (React)
    ↕ REST API
Backend (Node.js + Express)
    ↕
Database (PostgreSQL / MongoDB)

---

## 3. Component Design

### 3.1 Frontend

Components:
- SearchForm
- LawyerCard
- FilterPanel
- LawyerProfile
- Navbar
- Footer

Responsibilities:
- Collect user input
- Display filtered lawyer results
- Provide clear navigation

---

### 3.2 Backend

Modules:
- Authentication Service
- Lawyer Management Service
- Search & Ranking Service
- Review Management Service

Responsibilities:
- Process user queries
- Filter and rank lawyers
- Manage user data
- Ensure data integrity

---

## 4. Database Design

### 4.1 Lawyer Table

| Field | Type | Description |
|-------|------|------------|
| id | UUID | Primary key |
| name | String | Lawyer name |
| qualification | String | Academic details |
| specialization | String | Case types |
| experience_years | Integer | Experience |
| success_rate | Float | Percentage |
| avg_case_duration | Integer | Months |
| charges | Decimal | Fee structure |
| location | String | City |
| rating | Float | Average rating |

---

## 5. Ranking Logic (Initial)

Score = 
- Case Match Weight (40%)
- Budget Compatibility (20%)
- Location Match (20%)
- Rating (10%)
- Experience (10%)

Future: Replace with ML-based ranking model.

---

## 6. Security Design

- JWT-based authentication
- Role-based access control
- Encrypted database storage
- Admin approval workflow

---

## 7. Scalability Strategy

- Modular services
- Cloud deployment ready
- API-first architecture for future mobile app

---

## 8. Future App Integration

The backend API will be reusable for:
- Android App
- iOS App
- Real-time notifications
- Online booking
