Employee Onboarding Automation
End-to-end employee onboarding automation built with n8n, ASP.NET Core Web API, SQL Server, and Gmail Integration. The workflow automates employee registration, validation, email notification, audit logging, and API orchestration through a secure and scalable process.

Project Overview
This project demonstrates how business processes can be automated by integrating workflow orchestration with backend services.

When a new employee onboarding request is submitted, the workflow:

Receives the request through a webhook.
Validates incoming data.
Authenticates with the Employee Management API.
Creates a new employee record.
Sends an onboarding confirmation email.
Records audit information.
Returns a success or failure response.
The solution showcases real-world automation scenarios commonly found in HR, ERP, and enterprise systems.

Architecture
                            +------------------+
                            | Client / HR User |
                            +---------+--------+
                                      |
                                      v
                          +----------------------+
                          |    n8n Workflow      |
                          |  (Docker Container)  |
                          +----------+-----------+
                                     |
                                     v
                      +-----------------------------+
                      | Input Validation & Rules    |
                      +-------------+---------------+
                                    |
                                    v
                      +-----------------------------+
                      | ASP.NET Core Employee API   |
                      | JWT Authentication          |
                      +-------------+---------------+
                                    |
                     +--------------+--------------+
                     |                             |
                     v                             v
          +--------------------+      +--------------------+
          | SQL Server         |      | Gmail Integration  |
          | Employee Database  |      | Email Notification |
          +--------------------+      +--------------------+
                     |
                     v
          +--------------------+
          | Employee Audit Log |
          +--------------------+
                     |
                     v
          +--------------------+
          | Webhook Response   |
          +--------------------+

Development Environment:
- n8n running in Docker
- API exposed externally using ngrok
Workflow Process
1. Receive Request
The workflow starts when a webhook receives employee onboarding data.

2. Data Validation
Business rules validate employee information such as:

Email format
Required fields
Employee attributes
3. Authentication
The workflow authenticates against the Employee Management API using JWT.

4. Employee Creation
Validated employee information is sent to the Employee API.

5. Email Notification
A confirmation email is automatically sent to the employee.

6. Audit Logging
The workflow stores onboarding activity logs for traceability.

7. Response
The workflow returns a success or error response to the caller.

Features
Webhook-based processing
Employee onboarding automation
JWT authentication
REST API integration
Business rule validation
Email validation
Automated Gmail notifications
Audit logging
Error handling
End-to-end workflow orchestration
Technology Stack
Workflow Automation
n8n
Backend
ASP.NET Core
C#
Entity Framework Core
JWT Authentication
SQL Server
Integration
REST API
Webhook
Gmail
Development Tools
Docker
Swagger/OpenAPI
Postman
ngrok
Related API Repository
This workflow integrates with the Employee Management API:

🔗 https://github.com/Alr3y/Employee-Management-Systems

Development Environment
n8n
The workflow is executed inside a Docker container.

API
ASP.NET Core Web API runs locally and provides employee management endpoints.

External Access
During development and testing, ngrok is used to expose local API endpoints to the internet, allowing n8n and external clients to access the API securely.

Sample Request
{
  "firstName": "Aldi",
  "lastName": "Renaldi",
  "email": "arenaldi006@gmail.com",
  "phone": "08123456789",
  "hireDate": "2026-10-17T00:00:00Z",
  "salary": 10000000,
  "departmentId": 2,
  "isActive": true
}
Sample Response
{
  "employeeId": 20,
  "firstName": "Aldi",
  "lastName": "Renaldi",
  "email": "arenaldi006@gmail.com",
  "status": "Success"
}
Business Value
This automation reduces manual HR activities by:

Eliminating repetitive data entry
Improving onboarding consistency
Reducing processing time
Providing audit transparency
Automating employee communication
Improving operational efficiency
Screenshots
Workflow Automation
screenshots/workflow.png

API Integration
screenshots/api-success.png

Email Notification
screenshots/email-notification.png

Architecture Diagram
screenshots/architecture.png

Repository Structure
employee-onboarding-automation
│
├── README.md
│
├── screenshots
│   ├── architecture.png
│   ├── workflow.png
│   ├── api-success.png
│   └── email-notification.png
│
└── n8n
    └── employee-onboarding.json
Key Learning Outcomes
This project demonstrates practical experience in:

Workflow Automation
API Integration
Backend Development
JWT Authentication
Docker Deployment
Webhook Processing
Email Automation
Process Orchestration
Enterprise Integration Patterns
Author
Aldi Renaldi

.NET Developer | Integration & Workflow Automation Enthusiast | Automation Engineer