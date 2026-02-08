# TriFalconFitness – Project Documentation

---

## 1. Executive Summary & Project Overview

### 1.1 Goals and Objectives

**Software Goals**
- Provide a web-based platform for users to:
  - Track workouts and physical activity
  - Record nutrition notes
  - Monitor wellness metrics over time
- Centralize fitness and wellness data in a single application
- Ensure secure user authentication and data protection

**Developer Goals**
- Build a maintainable ASP.NET Core MVC application
- Deploy and manage the application using Microsoft Azure
- Apply industry-standard practices for authentication, deployment, and documentation
- Create reusable documentation to support future development

**Business Goals**
- Demonstrate a viable fitness tracking web application
- Lay the foundation for future enhancements and potential monetization
- Provide a scalable solution suitable for broader user adoption

---

### 1.2 Key Stakeholders and Their Roles

| Stakeholder | Role | Responsibilities |
|------------|-----|------------------|
| Don Tran | Business Owner / Developer | Repository management, Development, documentation, deployment support |
| Tiyler Miller | Business Owner / Developer | Repository management, Development, documentation, deployment support |
| Alexis Norman | Business Owner / Developer | Repository management, Development, documentation, deployment support |
| End Users | Primary Users | Track workouts, nutrition, and wellness data |
| Instructor | Reviewer | Evaluation and feedback |

**Primary User Expectations**
- Easy-to-use web interface
- Secure login and data privacy
- Reliable access across modern browsers
- Consistent performance

---

### 1.3 Business Value and Expected Outcomes

**Business Value**
- Reduces the need for multiple fitness and wellness tools
- Saves users time by consolidating health tracking
- Demonstrates a marketable Software-as-a-Service (SaaS) fitness concept
- Provides a cost-effective solution using free-tier cloud hosting

**Expected Outcomes**
- Successful deployment on Microsoft Azure
- Functional tracking of fitness and wellness data
- Positive user experience with secure data handling
- Complete and maintainable project documentation

---

### 1.4 Critical Success Factors

The project is considered successful if:
- The application deploys successfully to Azure App Service
- Users can securely register, log in, and manage personal data
- Core features function reliably within Azure Free (F1) tier limits
- Documentation supports setup, maintenance, and replication
- The system is stable and accessible via supported browsers

---

## 2. System Architecture

### 2.1 Client-Side Architecture

- **Application Type:** Browser-based web application
- **User Interface:** Responsive web UI using Bootstrap
- **Supported Browsers:** Chrome, Edge, Firefox (latest versions)
- **Supported Devices:** Desktop and tablet (mobile responsive design)
- **Client-Side Technologies:**
  - ASP.NET Core MVC (Razor Views)
  - Bootstrap for UI styling
- **Local Storage Requirements:**
  - Session data managed via ASP.NET Core Session and Identity cookies
  - No persistent client-side storage required

---

### 2.2 Server-Side Architecture

- **Programming Language & Runtime:** C# / .NET 10.0
- **Framework:** ASP.NET Core MVC
- **Web Server:** IIS
- **API Specifications:**
  - REST-style endpoints for user and fitness data
  - Internal MVC controllers used for request handling
- **Database Design:**
  - Relational database hosted on Azure SQL
  - Entities include Users, Workouts, Activities, Nutrition Entries
- **Authentication & Authorization:**
  - ASP.NET Core Identity
  - Role-based access control
- **Third-Party Integrations:**
  - None currently implemented
- **Hosting Requirements:**
  - Microsoft Azure App Service (Free F1 SKU)
  - Azure-managed SSL certificate (DigiCert)

---

## 3. Functional Requirements

### 3.1 User Stories / Use Cases

**Use Case: Log Workout**
- **Actor:** Authenticated User
- **Preconditions:** User is logged in
- **Flow of Events:**
  1. User navigates to workout log page
  2. User enters workout details
  3. User submits the form
- **Post Conditions:** Workout data is saved to the database
- **Exception Cases:** Invalid or missing input data

---

### 3.2 Business Rules

- **Data Validation Rules:**
  - Required fields must be completed
  - Numeric values must be within acceptable ranges
- **Workflow Rules:**
  - Users must be authenticated to create or edit records
- **Access Control Rules:**
  - Users may only access their own data
- **Business Logic Constraints:**
  - Duplicate entries are restricted where applicable

---

## 4. Non-Functional Requirements

### 4.1 Performance Requirements

- **Response Time:** Page loads within 3 seconds under normal load
- **Throughput:** Supports basic CRUD operations for all users
- **Concurrent Users:** Limited by Azure Free tier capacity

---

### 4.2 Security Requirements

- **Authentication Methods:** ASP.NET Core Identity
- **Authorization Levels:** User-based access control
- **Data Encryption:**
  - HTTPS (TLS) for data in transit
  - Azure-managed encryption at rest
- **Security Compliance:** Adheres to basic web security best practices

---

### 4.3 Scalability and Availability

- **Uptime Requirements:** Best-effort availability under free-tier SLA
- **Load Handling:** Designed for small user base
- **Backup and Recovery:** Manual snapshots via Azure Portal
- **Geographic Distribution:** Single Azure region (Canada Central)

---

## 5. Data Management

- **Data Models:** Users, Workouts, Activities, Nutrition Logs
- **Relationships:** One-to-many relationships between users and entries
- **Data Retention:** Data retained while account is active
- **Privacy Requirements:** User data accessible only by account owner
- **Backup Strategy:** Manual backups via Azure

---

## 6. Interface Specifications

### 6.1 API Documentation

- **Endpoints:** Internal MVC controller routes
- **Request/Response Format:** HTTP requests with Razor Views
- **Error Handling:** Server-side validation and error pages
- **Rate Limiting:** Not implemented (free-tier constraints)

---

### 6.2 External Interfaces

- **Integration Points:** None
- **Communication Protocols:** HTTPS

---

## 7. Infrastructure Requirements

- **Development Environment:** Visual Studio 2022/2026, .NET 10 SDK
- **Testing Environment:** Local developer machines
- **Staging Environment:** None
- **Production Environment:** Azure App Service
- **Deployment:** `dotnet build` and Azure publish profile

---

## 8. Quality Assurance

- **Testing Requirements:** Manual functional testing
- **Acceptance Criteria:** Core features operate without errors
- **Performance Metrics:** Page load times and error rates
- **Code Quality Standards:** Clean MVC separation and naming conventions
- **Security Testing:** Authentication and access verification

---

## 9. Documentation Needs

- Technical documentation
- User documentation
- API documentation
- Deployment documentation
- Maintenance documentation

---

## 10. Project Constraints and Assumptions

### Technical Constraints
- Limited resources due to Azure Free tier
- No containerization or advanced CI/CD

### Business Constraints
- No external funding
- Academic project scope

### Timeline Constraints
- Semester-based delivery schedule

### Resource Constraints
- Small development team
- Limited testing resources

### Dependencies
- Microsoft Azure availability
- .NET framework updates
