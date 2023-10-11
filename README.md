## **Niftables-Backend Project**

---

**Name**: niftables-backend  
**Version**: 0.7.a  
**Description**: The Niftables Backend project, developed using the powerful NestJS framework, serves as a comprehensive backend solution tailored for the evolving NFT (Non-fungible Token) marketplaces. It incorporates a myriad of functionalities to ensure seamless operations, right from user authentication to final NFT transactions.

**Technical Features and Modules:**

1. **Diverse Payment Alternatives**:
    - **Cryptocurrency Payments**: The project harnesses the Ethereum blockchain to enable crypto transactions.
    - **Fiat Payments**: Integrating Moonpay, a renowned fiat-crypto gateway, ensures that users can also pay using traditional currency methods.

2. **Wallet Management**:
    - For users who don't already possess a digital wallet, the system is designed to automatically generate one, courtesy of Fireblocks, a digital asset security platform.

3. **Auth Module**:
    - **User Authentication & Authorization**: It employs JWT (JSON Web Tokens) for authentication and maintains user sessions.
    - **Crypto Wallet Interaction**: Users can link their existing digital wallets.
    - **Wallet Creation**: As mentioned, for users without a wallet, the module can generate one, ensuring a wider user base can engage with NFT transactions.

4. **Core Module**:
    - **Payment Processing**: It can process payments, accommodating both cryptocurrency and fiat, ensuring flexibility for end-users.
    - **Withdrawal Management**: Users can initiate and process withdrawals from their account.
    - **NFT Statistics**: Provides detailed statistics on NFTs, crucial for users and marketplace admins alike.
    - **IPFS & Pinata Integration**: For decentralized storage and ensuring NFT data permanence, the system seamlessly interacts with the IPFS (InterPlanetary File System) API via Pinata, a decentralized data storage service.

5. **Real-time Currency Rates**:
    - To keep users informed and ensure transparent transactions, the backend fetches real-time currency rates using the Coinmarketcap API, a reliable source for cryptocurrency market cap rankings and more.

6. **Code Quality & Maintenance**:
    - The project's `package.json` also suggests rigorous code quality checks with ESLint and Prettier. Moreover, the testing suite with Jest ensures the robustness of the system. Lint-staged further ensures that only linted code is committed, maintaining code quality.

---

## Api documentation

Detailed information about all backend API can be found here:
https://webmedia-georgia.github.io/superlotls-backend-docs/api.html

---

## Indexer documentation

Indexer documentation can be found by following this link:
[Indexer docs](INDEXER.md)

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
