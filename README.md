# Three-Tier-Architecture
## Tier One: The Presentation Tier - Frontend
This is the user interface and communication layer of the application, where the end-user interacts with the software. Its main purpose is to display information and to collect information from the user.

## Tier Two: The Application Tier - Backend
The application tier is the middle layer of 3 tier archictecture. It acts as intermediatery layer between the presentation tier and the data management tie.
## Tier Three: The Data Management Tier - Database
The Data management tier is the bottom layer of 3-tier architecture. It is responsible for managing and storing data  .
This tier include database, data warehouse and any other persistent data storage solution. 
## Why use 3 Tier architecture
- Scalability: You can grow each part of the system on its own. If you get more users, you only need to add more power to the "User Layer" without having to change the "Database Layer."
- Flexibility: The layers are separate, so you can change or upgrade one without breaking the others. For example, you can switch your database type (like moving from MySQL to PostgreSQL) without needing to change your website code.
- Security: The database is hidden behind the other layers. Users cannot touch the data directly; they have to go through the "Application Layer" first, which keeps the sensitive information safe.
- maintainbality: Because the system is built in pieces, it is easier to fix and update. Different developers can work on different layers at the same time without getting in each other's way.
- Performance: Each layer is designed to do only one specific job. This focus allows every part of the system to be optimized so the whole application runs faster.
