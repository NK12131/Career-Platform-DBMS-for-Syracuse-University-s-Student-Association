# Student Association DBMS
### Syracuse University · Career Opportunities Platform

> A centralized database management system connecting students with internships, part-time jobs, and co-op opportunities built for the Syracuse University Student Association.

---

## The Problem

Students and employers at Syracuse lack a unified platform for opportunity discovery and application management. The current state:

- Students manually search fragmented sources for internships, part-time, and co-op roles
- Employers have no structured channel to reach qualified SU candidates
- Event coordination, feedback collection, and member management all run on inefficient manual workflows

---

## The Solution

A tailored DBMS that centralizes every touchpoint in the student–employer pipeline: opportunity listings, applications, event coordination, feedback, and association member management, all in one place.

**Who benefits:**

| User | What they get |
|------|---------------|
| Students | Single dashboard for opportunities, applications, and events |
| Employers | Streamlined posting + access to a vetted candidate pool |
| Association Members | Role and responsibility management tools |
| Administrators | Analytics, reporting, and system oversight |

---

## Data Model

### Entities & Attributes

**Student**
```
StudentID (PK) · FirstName · LastName · ContactInfo · Major · GraduationYear
```

**Employer**
```
EmployerID (PK) · CompanyName · ContactInfo · Industry
```

**Opportunity**
```
OpportunityID (PK) · Title · Description · Type [Internship | Part-time | Co-op] · Duration · Stipend/Salary
```

**Application**
```
ApplicationID (PK) · StudentID (FK) · OpportunityID (FK) · Resume · CoverLetter · Status [Pending | Accepted | Rejected]
```

**Event**
```
EventID (PK) · Title · DateTime · Location · Description
```

**Feedback**
```
FeedbackID (PK) · StudentID (FK) · OpportunityID (FK) · Rating · Comments
```

**Association Member**
```
MemberID (PK) · StudentID (FK) · Position · Responsibilities
```

### Relationships

```
Student ──< Application >── Opportunity
Student ──< Feedback    >── Opportunity
Student ──< Association Member
Employer ──< Opportunity
```

---

## Key Features

- **Opportunity Discovery**:  searchable, filterable listings by type, industry, and duration
- **Application Tracking**:  status updates (Pending → Accepted/Rejected) with resume and cover letter storage
- **Event Management**:  create, schedule, and manage career fairs and networking events
- **Feedback Loop**: structured post-opportunity ratings and comments from students
- **Member Portal**: role assignment and responsibility tracking for association officers
- **Reporting & Analytics**: engagement metrics, application outcomes, and employer activity dashboards

---

## Future Enhancements

- [ ] Resume parsing and keyword-based opportunity matching
- [ ] Email/SMS notifications for application status changes
- [ ] Employer ratings by students (two-way feedback)
- [ ] Integration with Handshake or LinkedIn APIs
- [ ] Role-based access control (RBAC) per user type

---

## Context

Developed as a database design proposal for the IST program at Syracuse University's School of Information Studies. Intended as a blueprint for a production system to serve the SU Student Association.
