# ATM-Bank-Management-System

![GitHub Workflow Status](https://img.shields.io/badge/status-in%20progress-orange) ![Language](https://img.shields.io/badge/language-Java-red) ![Microservices](https://img.shields.io/badge/framework-SpringBoot-green)
![RestTemplate](https://img.shields.io/badge/RestTemplate-darkgreen) ![PostgreSQL](https://img.shields.io/badge/database-PostgreSQL-blue)

***This project is still in progress and under active development.***

---

## Microservices

The system consists of **5 main microservices**:

| Service | Description | GitHub Link |
| ------- | ----------- | ----------- |
| Auth Service | Handles user registration, login, logout, and token management. Communicates with Card and Notification services to create cards and send registration notifications | [Auth Service](https://github.com/alyvnihad/ATM-Auth-Service) |
| Account Service | Manages user accounts including creation, deposit, withdraw, balance inquiry, and transfer limits. Communicates with TransactionService to log transactions | [Account Service](https://github.com/alyvnihad/ATM-Account-Service) |
| Card Service | Handles card creation, PIN verification, blocking and unblocking of cards. Communicates with AccountService to create accounts linked to new cards| [Card Service](https://github.com/alyvnihad/ATM-Card-Service) |
| Transaction Service | Logs all account transactions (deposit, withdraw, transfer) and provides transaction history for accounts | [Transaction Service](https://github.com/alyvnihad/ATM-Transaction-Service) |
| ATM Service | Manages ATM operations including login, deposit, withdraw, balance inquiry, and logout through communication with Auth and Account services | [ATM Service](https://github.com/alyvnihad/ATM-Atm-Service) |

---

## Tech Stack

- **Language:** Java  
- **Framework:** Spring Boot (Microservices Architecture)  
- **Database:** PostgreSQL  
- **Communication:** REST (via RestTemplate)  
- **Security:** JWT Authentication  
- **Dependency Management:** Maven

---

## License

*This project you are free to use, modify, and distribute the code, but the **author retains copyright**.* 
