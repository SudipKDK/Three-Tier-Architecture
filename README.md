# Three-Tier-Architecture
## Tier One: The Presentation Tier - Frontend
This is the user interface and communication layer of the application, where the end-user interacts with the software. Its main purpose is to display information and to collect information from the user.

## Tier Two: The Application Tier - Backend
The application tier is the middle layer of 3 tier archictecture. It acts as intermediatery layer between the presentation tier and the data management tie.
## Tier Three: The Data Management Tier - Database
The Data management tier is the bottom layer of 3-tier architecture. It is responsible for managing and storing data  .
This tier include database, data warehouse and any other persistent data storage solution. 
## Why use 3 Tier architecture
- **Scalability**: You can grow each part of the system on its own. If you get more users, you only need to add more power to the "User Layer" without having to change the "Database Layer."
- **Flexibility**: The layers are separate, so you can change or upgrade one without breaking the others. For example, you can switch your database type (like moving from MySQL to PostgreSQL) without needing to change your website code.
- **Security**: The database is hidden behind the other layers. Users cannot touch the data directly; they have to go through the "Application Layer" first, which keeps the sensitive information safe.
- **maintainbality**: Because the system is built in pieces, it is easier to fix and update. Different developers can work on different layers at the same time without getting in each other's way.
- **Performance**: Each layer is designed to do only one specific job. This focus allows every part of the system to be optimized so the whole application runs faster.

# Three Tier Web Architecture in AWS
<img width="1022" height="1051" alt="3tierArch" src="https://github.com/user-attachments/assets/4badfdcf-c45e-4ba9-951c-2e0219c91cf1" />

1. **The Web Tier (Public Subnet):**  
This is the entry point for users. In AWS, this tier typically consists of a Load Balancer and a set of EC2 instances or S3-hosted static files.
- AWS Services: Amazon Route 53, Application Load Balancer (ALB), Amazon CloudFront.
- Networking: These resources sit in Public Subnets. They have a route to an Internet Gateway to communicate with the outside world.
- Security: Security Groups allow incoming traffic on port 80 (HTTP) or 443 (HTTPS) from the internet.
2. **The Application Tier (Private Subnet)**
This is where your "business logic" lives . It is isolated from the public internet for security.
- AWS Services: EC2, AWS Lambda, or Amazon ECS/EKS.
- Networking: These resources sit in Private Subnets. They cannot be reached directly from the internet. If they need to download updates or reach external APIs, they go through a NAT Gateway located in the Public Subnet.
- Security: Security Groups are configured to only allow traffic from the Web Tier’s Load Balancer.
3. **The Data Tier (Private Subnet)**
This is the deepest layer, where your data is persisted.
- AWS Services: Amazon RDS, Amazon Aurora, or Amazon DynamoDB.
- Networking: Also located in Private Subnets. To ensure high availability, RDS is usually deployed in a Multi-AZ configuration, which automatically replicates data to a standby instance in a different AZ.
- Security: Security Groups are the most restrictive here, allowing traffic only from the Application Tier on specific database ports.
