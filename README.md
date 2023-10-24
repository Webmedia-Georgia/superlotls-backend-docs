## **Niftables-Backend Project**

---

**Name**: niftables-backend  
**Version**: 0.7.a  
**Description**: The Niftables Backend project, developed using the powerful NestJS framework, serves as a comprehensive backend solution tailored for the evolving NFT (Non-fungible Token) marketplaces. It incorporates a myriad of functionalities to ensure seamless operations, right from user authentication to final NFT transactions.

- [Technical Features and Modules](#technical-features-and-modules)
- [NestJs Modules](#nestjs-modules)
- [Auth Module](#auth-module)
    * [User Authentication & Authorization](#user-authentication---authorization)
        + [JWT (JSON Web Tokens)](#jwt--json-web-tokens-)
    * [Crypto Wallet Interaction](#crypto-wallet-interaction)
        + [Linking Existing Digital Wallets](#linking-existing-digital-wallets)
        + [Wallet Creation](#wallet-creation)
- [Core Module](#core-module)
    * [Payment Processing](#payment-processing)
    * [Withdrawal Management](#withdrawal-management)
    * [NFT Statistics](#nft-statistics)
    * [IPFS & Pinata Integration](#ipfs-pinata-integration)
- [Database Schema Overview](#database-schema-overview)
    * [1. NFT Minting](#1-nft-minting)
        + [Purpose](#purpose)
        + [Tables](#tables)
    * [2. User Authentication & Authorization (Auth)](#2-user-authentication-and-authorization)
        + [Purpose](#purpose-1)
        + [Tables](#tables-1)
    * [3. Payment Processing](#3-payment-processing)
        + [Purpose](#purpose-2)
        + [Tables](#tables-2)
    * [4. Chain Indexing](#4-chain-indexing)
        + [Purpose](#purpose-3)
        + [Tables](#tables-3)
- [Api documentation](#api-documentation)
- [Indexer documentation](#indexer-documentation)
- [AWS Deployment Architecture](#aws-deployment-architecture)
    * [1. Core API](#1-core-api)
    * [2. Auth API](#2-auth-api)
    * [3. Chain Indexer](#3-chain-indexer)
    * [Database Infrastructure:](#database-infrastructure)
- [Setup & Building Instructions](#setup---building-instructions)
    * [1. Prerequisites](#1-prerequisites)
    * [2. Installation](#2-installation)
    * [3. Building](#3-building)
    * [4. Running the Project](#4-running-the-project)
    * [5. Testing](#5-testing)
    * [6. Linting](#6-linting)
    * [Additional Scripts](#additional-scripts)


## Technical Features and Modules

1. **Diverse Payment Alternatives**:
    - **Cryptocurrency Payments**: The project harnesses the Ethereum blockchain to enable crypto transactions.
    - **Fiat Payments**: Integrating Moonpay, a renowned fiat-crypto gateway, ensures that users can also pay using traditional currency methods.

2. **Wallet Management**:
    - For users who don't already possess a digital wallet, the system is designed to automatically generate one, courtesy of Fireblocks, a digital asset security platform.

3. **User Authentication & Authorization**:
    - It employs JWT (JSON Web Tokens) for authentication and maintains user sessions.

4. **Crypto Wallet Interaction**:
   - Users can link their existing digital wallets.

5. **Wallet Creation**:
   - As mentioned, for users without a wallet, the module can generate one, ensuring a wider user base can engage with NFT transactions.

6. **Payment Processing**:
   - It can process payments, accommodating both cryptocurrency and fiat, ensuring flexibility for end-users.

7. **Withdrawal Management**:
   - Users can initiate and process withdrawals from their account.

8. **NFT Statistics**:
   - Provides detailed statistics on NFTs, crucial for users and marketplace admins alike.

9. **IPFS & Pinata Integration**:
   - For decentralized storage and ensuring NFT data permanence, the system seamlessly interacts with the IPFS (InterPlanetary File System) API via Pinata, a decentralized data storage service.

10. **Real-time Currency Rates**:
     - To keep users informed and ensure transparent transactions, the backend fetches real-time currency rates using the Coinmarketcap API, a reliable source for cryptocurrency market cap rankings and more.

11. **Code Quality & Maintenance**:
     - The project's `package.json` also suggests rigorous code quality checks with ESLint and Prettier. Moreover, the testing suite with Jest ensures the robustness of the system. Lint-staged further ensures that only linted code is committed, maintaining code quality.

---

## NestJs Modules

The Auth and Core Modules together form the backbone of our application, providing essential features for user authentication, NFT transactions, and account management. These modules ensure a secure and seamless experience for all users while maintaining the integrity and permanence of NFT data through decentralized storage.


## Auth Module

The Auth Module is an integral part of our application, responsible for user authentication, authorization, and crypto wallet management. This module ensures the security of user data and transactions while providing a seamless experience for both new and existing users.

### User Authentication And Authorization

#### JWT (JSON Web Tokens)

The Auth Module employs JWT for user authentication and authorization. Here's how it works:

1. **User Registration**: New users can sign up with their email and password.
2. **User Login**: Registered users can log in using their credentials.
3. **Token Generation**: Upon successful login, the module generates a JWT containing user information and permissions.
4. **Token Validation**: Incoming requests are validated against the JWT to ensure the user is authorized to perform the requested actions.

### Crypto Wallet Interaction

#### Linking Existing Digital Wallets

Users have the option to link their existing digital wallets to the application. This allows them to seamlessly interact with their cryptocurrency assets within the system.

#### Wallet Creation

For users who don't have a digital wallet, the module offers wallet creation. This feature ensures that a wider user base can engage in NFT transactions, even if they are new to the crypto space.

## Core Module

The Core Module is at the heart of our application, providing essential features for NFT transactions and account management.

### Payment Processing

The Payment Processing feature ensures flexible payment options for our users, including both cryptocurrencies and fiat currencies. Here's how it works:

1. **Payment Initiation**: Users can initiate payments for NFT purchases.
2. **Currency Flexibility**: The module supports a variety of cryptocurrencies and fiat currencies, allowing users to choose their preferred payment method.
3. **Secure Transactions**: Payments are processed securely to protect user data and assets.

### Withdrawal Management

Users can easily manage their funds through the Withdrawal Management feature:

1. **Withdrawal Requests**: Users can initiate withdrawal requests from their accounts.
2. **Processing**: Withdrawals are processed efficiently and securely.
3. **Transaction History**: Users can track their withdrawal history for transparency.

### NFT Statistics

The NFT Statistics feature provides detailed insights into NFTs, benefiting both users and marketplace administrators. Here's what it offers:

1. **Comprehensive Data**: Users can access statistics such as NFT transaction volume, popular NFT categories, and more.
2. **Market Insights**: Marketplace administrators can use these statistics to make informed decisions and improve the user experience.

### IPFS And Pinata Integration

To ensure the permanence and decentralization of NFT data, our application seamlessly integrates with the IPFS (InterPlanetary File System) API via Pinata, a decentralized data storage service.

1. **Data Storage**: NFT data is securely stored on the IPFS network, guaranteeing its availability and resilience.
2. **Pinata Integration**: The integration with Pinata enhances data storage reliability and accessibility.
3. **Data Retrieval**: Users can access NFT data with confidence, knowing that it is stored securely on a decentralized network.

---

## Database Schema Overview

Full database structure diagram can be found by following this link:
https://webmedia-georgia.github.io/superlotls-backend-docs/db.html

The database schema has been meticulously designed to encompass four crucial components:
- **NFT Minting**
- **User Authentication & Authorization (Auth)**
- **Payment Processing**
- **Chain Indexing**

Each of these components is essential for the holistic functioning of the system, facilitating a diverse range of operations from NFT management to blockchain interactions.

### 1. NFT Minting

#### Purpose
This component plays a pivotal role in consolidating NFT data from a multitude of collections. The primary objective is to assimilate this data and subsequently link it to users during the withdrawal procedures.

#### Tables
- `nft_metadata`: Captures detailed metadata associated with each NFT.
- `withdrawal`: Tracks the withdrawal requests of NFTs by users.
- `mint_schedule`: Regulates and logs the minting schedules for different NFTs.
- `nft`: Maintains a record of individual NFTs.
- `collection`: Classifies NFTs into distinct collections.
- `payment`: Manages payment information related to NFT transactions.

### 2. User Authentication and Authorization

#### Purpose
This module is responsible for ascertaining user identities and granting appropriate permissions. Furthermore, it provides a structured framework for defining user groups and configuring specific settings such as NFT pricing for different groups.

#### Tables
- `user`: Contains essential user details and credentials.
- `email_confirmation`: Logs email verification processes to ensure the authenticity of a user's email address.
- `user_groups`: Classifies users into predefined groups.
- `group_to_price`: Maps user groups to distinct NFT price brackets.
- `user_settings`: Stores personalized settings and preferences for each user.

### 3. Payment Processing

#### Purpose
Primarily designed to oversee transactional processes, this component also serves as a repository for information pertinent to smart contracts.

#### Tables
- `contract_deposit`: Keeps a ledger of deposits made under various contracts.
- `nonce_confirmation`: Records and verifies unique transaction identifiers to prevent double-spending and ensure the integrity of transactions.

### 4. Chain Indexing

#### Purpose
This module is integral to the indexing subsystem, allowing for the precise indexing of the Ethereum blockchain. It meticulously captures and stores relevant transactional data.

#### Tables
- `chain_indexing`: Acts as the primary data storage for indexed Ethereum blockchain transactions, ensuring a streamlined retrieval of transactional data for system operations.

---

With these components, the database schema offers a robust foundation for seamless operations, from user interactions to blockchain engagements.

---

## Api documentation

Detailed information about all backend API can be found here:
https://webmedia-georgia.github.io/superlotls-backend-docs/api.html

---

## Indexer documentation

Indexer documentation can be found by following this link:
[Indexer docs](INDEXER.md)

---

## **AWS Deployment Architecture**

In this AWS environment, we've intricately woven the capabilities of various AWS services, majorly centering on the Amazon Elastic Container Service (ECS) for container orchestration. Let's delve deeper into this technical breakdown:
Follow this link to see deployment diagram:
https://webmedia-georgia.github.io/superlotls-backend-docs/aws.html


### **1. Core API**

- **Deployment Platform**:
    - Deployed on **Amazon ECS**—the managed service supporting Docker containers, enabling easy execution of applications on a cluster of Amazon EC2 instances.

- **Load Balancing**:
    - Incorporates **Amazon Elastic Load Balancing (ELB)**, specifically the **Application Load Balancer (ALB)** variant to uniformly distribute incoming HTTP/HTTPS traffic across ECS tasks.

- **Service Auto Scaling**:
    - Enabled with target tracking scaling policies, accommodating up to 10 tasks under heightened load, monitored through CloudWatch metrics.

- **Networking**:
    - Operates in a VPC with security groups allowing only essential inbound traffic, ensuring robust security.

### **2. Auth API**

- **Deployment Platform**:
    - Also orchestrated through **Amazon ECS**.

- **Load Balancing**:
    - Employs an **Application Load Balancer (ALB)**, managing authentication request traffic for optimal routing and minimized latency.

- **Service Auto Scaling**:
    - Equipped with auto-scaling to spawn up to 10 ECS tasks based on demand, with oversight from Amazon CloudWatch.

- **Networking**:
    - Resides within the same VPC as Core API, fortified by security groups that regulate inbound traffic.

### **3. Chain Indexer**

- **Deployment Platform**:
    - Consistently deployed on **Amazon ECS**.

- **Load Balancing**:
    - Distinctly does not incorporate ELB, catering to its specific operational paradigm.

- **Instance Configuration**:
    - Runs as a singleton task, ensuring sequential and consistent operations.

- **Networking**:
    - While it bypasses load balancing, it still functions within the VPC, safeguarded by pertinent security groups.

### **Database Infrastructure**:

All services pivot around a central **PostgreSQL database**:

- **Hosting**:
    - The database finds its home on **Amazon RDS**, offering features like automated backups, snapshots, host replacement, and resizing.

- **Configuration**:
    - Positioned within a Multi-AZ setup for high availability. AWS Secrets Manager handles database credentials securely.

- **Networking**:
    - Located in a private subnet in the VPC, shielding it from direct public internet access.

---

In essence, this architecture capitalizes on the robust offerings of AWS, especially with ECS at its core for container management and RDS for seamless database operations, ensuring high availability, scalability, and streamlined operations.

---

## **Setup & Building Instructions**

### **1. Prerequisites**

- Ensure Node.js is installed on your machine.

### **2. Installation**

Navigate to the project directory and install all required dependencies:

```bash
npm install
```

### **3. Building**

Build the project with:

```bash
npm run build
```

### **4. Running the Project**

- **Core API**:
  ```bash
  npm run start:core-api
  ```

- **Wallet**:
  ```bash
  npm run start:wallet
  ```

- **Auth API**:
  ```bash
  npm run start:auth-api
  ```

### **5. Testing**

- Execute tests:
  ```bash
  npm run test
  ```

- Run tests with coverage report:
  ```bash
  npm run test:cov
  ```

### **6. Linting**

Ensure the code meets linting standards:

```bash
npm run lint
```

For automatic lint issue fixes:

```bash
npm run lint:fix
```

### **Additional Scripts**

- **Format Code**:
  ```bash
  npm run format
  ```

- **Type Checking**:
  ```bash
  npm run type-check
  ```

---

**Note**: For specific configurations or environment setups needed, refer to the project's documentation or README file.

---
