# ATM-Bank-Management-System

![GitHub Workflow Status](https://img.shields.io/badge/status-in%20progress-orange) ![Language](https://img.shields.io/badge/language-Java-red) ![Microservices](https://img.shields.io/badge/framework-SpringBoot-green)
![RestTemplate](https://img.shields.io/badge/RestTemplate-darkgreen) ![PostgreSQL](https://img.shields.io/badge/database-PostgreSQL-blue)

***This project is still in progress and under active development.***

---

## Microservices

The system consists of **8 main microservices**:

| Service | Description | GitHub Link |
| ------- | ----------- | ----------- |
| API Gateway | Routing, load balancing, and security for all services | [API Gateway](https://github.com/alyvnihad/ATM-API-Gateway) |
| Auth Service | Handles user registration, login, logout, and token management. Communicates with Card and Notification services to create cards and send registration notifications | [Auth Service](https://github.com/alyvnihad/ATM-Auth-Service) |
| Account Service | Manages user accounts including creation, deposit, withdraw, balance inquiry, and transfer limits. Communicates with TransactionService to log transactions | [Account Service](https://github.com/alyvnihad/ATM-Account-Service) |
| Card Service | Handles card creation, PIN verification, blocking and unblocking of cards. Communicates with AccountService to create accounts linked to new cards| [Card Service](https://github.com/alyvnihad/ATM-Card-Service) |
| Transaction Service | Logs all account transactions (deposit, withdraw, transfer) and provides transaction history for accounts | [Transaction Service](https://github.com/alyvnihad/ATM-Transaction-Service) |
| ATM Service | Manages ATM operations including login, deposit, withdraw, balance inquiry, and logout through communication with Auth and Account services | [ATM Service](https://github.com/alyvnihad/ATM-Atm-Service) |
| Notification Service | Handles email notifications for registrations and transactions, including PDF attachments and security alerts | [Notification Service](https://github.com/alyvnihad/ATM-Notification-Service) |
| Report Service | Generates PDF account information reports for users using data from account and card services. | [Report Service](https://github.com/alyvnihad/ATM-Report-Service) |

---

## Architecture

**ATM & Bank System Architecture**

**Flow:**  

1. API Gateway handles all incoming requests.  
2. Auth Service manages authentication and JWT tokens.  
3. Account Service manages account registration, deposits, withdrawals, balances, and generates unique account numbers.
4. Card Service manages card creation, PIN checks, and admin block/unblock actions.
5. Transaction Service manages transaction logs, allows searching by transaction ID or account ID, and provides daily transaction reports
6. ATM Service provides login, logout, deposit, withdraw, and balance check with session management.
7. Notification Service handles sending registration emails with PDF attachments and transaction notification emails.
8. Report Service generates PDF register (iText) generates Excel Daily log (Apache POI) .  


---
## Key Features

### API Gateway

- Load balancing and routing  
- Authentication and security for all endpoints  
- Microservice monitoring and logging  

### Auth Service

- User registration, login and logout 
- JWT-based authentication  
- Access token refresh mechanism  

### Account Service

- Register new customer accounts with unique account numbers
- Store account details: card number, email, balance, currency and transfer limits
- Deposit money and send transaction logs to Transaction Service
- Withdraw money while checking transfer limits and account balance
- Retrieve current account balance

### Card Service

- Register new cards and generate related account via Account Service
- Encode and store card PIN securely
- Assign a payment network (VISA or Master) and expiry date
- Retrieve card information by card number
- Check card PIN with automatic block after 3 failed attempts
- Block, unblock cards and reset failed PIN attempts (admin only). 

### Transaction Service

- Save transaction logs for deposits, withdrawals and transfers
- Send email notifications for each transaction via Notification Service
- Retrieve a transaction by its ID
- Retrieve all transactions for a specific account
- Provide daily transaction logs for reporting purposes

### ATM Service

- Handle ATM login and maintain session info with expiration
- Deposit money to customer accounts via Account Service
- Withdraw money from customer accounts via Account Service
- Check account balance via Account Service
- Logout and clear ATM session
- Enforce session expiration checks for security

### Notification Service

- Send registration emails with attached PDF documents
- Send transaction notification emails to users
- Mask sensitive card information in transaction emails
- Track email sending status in database
- Handle email sending errors with proper logging and exceptions

### ReportService

- Generates PDF documents containing customer account and card information using iText.
- Generates Excel reports for daily logs.
- Export Excel reports using Apache POI  

---

## Tech Stack

- **Language:** Java  
- **Framework:** Spring Boot (Microservices Architecture)  
- **Database:** PostgreSQL  
- **Communication:** REST (via RestTemplate)  
- **Security:** JWT Authentication  
- **Dependency Management:** Maven
- **iText** – PDF invoice generation  
- **Apache POI** – Excel reporting  
- **JavaMailSender** – Email sending  

---



## License

*This project you are free to use, modify, and distribute the code, but the **author retains copyright**.* 
