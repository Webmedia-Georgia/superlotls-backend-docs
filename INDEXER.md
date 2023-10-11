## **Supertlotls Indexer**

---

The "Supertlotls Indexer" is an intricate backend system, primarily aimed at the indexing and processing of Non-Fungible Tokens (NFTs) within the Ethereum network. Leveraging the power and efficiency of the Go programming language, this project interacts directly with the Ethereum blockchain by utilizing the Etherscan API.


### **System Description and Technical Details**

---

1. **Language and Framework:** The project is written in Go (often referred to as Golang), a statically typed, compiled language known for its simplicity, efficiency, and concurrency support.

2. **Blockchain Integration:**
    - Uses the `etherscanLib` to parse Ethereum logs, especially focusing on token transfer events.
    - The system fetches logs from Etherscan, a popular Ethereum blockchain explorer and API service, through the `ethscanClient` which is set up with the relevant network URL (Mainnet or Goerli).

3. **Token Processing System:**
    - The `TokenProcessor` class in `token_processor.go` manages the processing of each token event. It identifies if the token is newly minted or if its ownership has changed and updates the database accordingly.

4. **Database Handling:**
    - **PostgreSQL** is the primary database, utilized for its robustness and relational capabilities.
    - Database interactions are managed using the `pgx/v5` package which allows efficient communication with the PostgreSQL server.
    - The system manages multiple models like NFT collections, chain indexing, metadata, and user details. Each model corresponds to specific tables and functions in the database.
    - Chain indexing (`chain_indexing.go`) is a noteworthy feature that keeps track of the last block that was processed, ensuring continuity and avoiding re-processing of data.

5. **Configuration Management:**
    - The Viper library (`github.com/spf13/viper`) is employed to handle application configuration. It enables the application to read configuration variables dynamically from an environment file, allowing flexibility in different deployment environments.

6. **Concurrency:**
    - The system uses Go's goroutines for concurrent execution of tasks, ensuring efficient processing of logs and token updates.
    - The `errgroup` package is used to manage and synchronize multiple goroutines, ensuring that if one fails, others are gracefully shut down.

7. **Error Handling and Logging:**
    - Comprehensive error handling mechanisms are in place, which log detailed messages for any unexpected scenarios. This assists developers in tracing and resolving issues.

8. **Data Parsing and Transformation:**
    - The Ethereum transfer events are decoded using the `transfers_pipeline.go`, which extracts and transforms raw data into structured formats like the address involved, token ID, and transaction hash.

---

Files Breakdown:

- `main.go`: The entry point of the application. It sets up necessary configurations, database connections, initializes the token processing, and starts the Ethereum logs fetching process.

- `token_processor.go`: This handles the core logic for processing tokens (NFTs) retrieved from Ethereum logs. It updates the ownership of tokens and associates them with relevant metadata.

- `transfers_pipeline.go`: This decodes and parses the Ethereum transfer events to extract relevant information, such as the address involved and the token ID.

- `chain_indexing.go`: This manages the chain indexing mechanism, helping the system keep track of the last block number it processed, ensuring no block is processed twice.


In essence, the Niftables Golang Backend system is a robust solution designed for platforms dealing with Ethereum-based NFTs. It combines the power of Go with efficient data processing mechanisms, making it an ideal choice for high-performance and scalable NFT platforms.

### **Build and Test Instructions**

---

### Prerequisites:

1. **Go:** Ensure you have Go installed (preferably the latest version). You can download and install it from the [official site](https://golang.org/dl/).

2. **PostgreSQL:** Make sure you have PostgreSQL set up and running as the application interfaces with a PostgreSQL database.

3. **Configurations:** Before running the application, set up the configuration values in an `.env` file. Place this file in the `config` directory.

---

### Building the Project:

1. **Clone the Repository:**
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. **Download Dependencies:**
   To download the necessary packages and dependencies, run:
   ```bash
   go mod download
   ```

3. **Build the Application:**
   Build the main application executable using:
   ```bash
   go build -o niftables-backend main.go
   ```

   This command will generate an executable named `niftables-backend` in the current directory.

---

### Running Tests:

1. Before running the tests, ensure your database is correctly set up and the relevant configuration values (database DSN, contract address, API keys, etc.) are correctly set in the `.env` configuration file.

2. **Run Tests:** Execute the tests using:
   ```bash
   go test ./...
   ```

   This command will recursively run all tests in the current directory and its sub-directories.

3. For more detailed test output with verbose logging, use:
   ```bash
   go test -v ./...
   ```

---

### Running the Application:

After building the application:

1. **Run the Application:**
   ```bash
   ./niftables-backend
   ```

   This will start the application, and it will begin indexing and processing NFTs based on the configurations provided.

2. To check the application's operation, monitor the console for logs. These will provide real-time insights into the processing of NFT transactions, errors, and other essential activities.

---

### Notes:

- Regularly back up your database to prevent data loss.

- Update your `.env` configuration file as necessary, especially when there are changes to the Ethereum contract address, database credentials, or other critical parameters.

- Keep your Etherscan API key confidential to prevent misuse. If you're sharing your code, remember to omit sensitive keys from the configuration files.

Good luck with building and testing your Niftables Golang Backend System!
