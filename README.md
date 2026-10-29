# 🏦 Secure Banking Transaction System

A console-based banking application built with **Java 17, JDBC, and MySQL**, focusing on secure authentication, transactional integrity, concurrency control, and database performance.

## 🚀 Key Features

- **Atomic Transactions:** JDBC commit/rollback for reliable deposits, withdrawals, and transfers.
- **Concurrency Control:** `SELECT ... FOR UPDATE` and consistent lock ordering to prevent lost updates and reduce deadlocks.
- **Secure Authentication:** Salted BCrypt password hashing and role-based access control (`CUSTOMER`, `TELLER`, `ADMIN`).
- **Audit Logging:** Tracks successful operations and login attempts.
- **Data Integrity:** `BigDecimal`, MySQL `DECIMAL`, foreign keys, and database constraints.
- **SQL Injection Prevention:** Parameterized queries using `PreparedStatement`.
- **Performance Optimization:** Composite indexes and `EXPLAIN ANALYZE` benchmarking.
- **Automated Testing:** JUnit tests for banking operations, authorization, and concurrent transfers.

## 🛠️ Tech Stack

`Java 17` · `JDBC` · `MySQL 8` · `Maven` · `BCrypt` · `JUnit` · `JaCoCo`

## 🏗️ Architecture

The project follows a layered architecture with a console interface, service layer for business rules and authorization, DAO layer for database operations, and a transaction utility for commit/rollback management.

## 🧪 Testing

- 1,000 concurrent transfer attempts across 50 threads.
- 15 unauthorized-access scenarios.
- Integration tests for transactions, authentication, and audit logging.
- JaCoCo code coverage reporting.
- SQL performance benchmarking with 100,000 transaction records.

*Report actual passing results and coverage after running the tests.*

## ⚙️ Setup & Run

**Prerequisites:** JDK 17+, Maven 3.8+, and MySQL 8.

```bash
mysql -u root -p < sql/schema.sql

export BANK_DB_URL="jdbc:mysql://localhost:3306/bankdb"
export BANK_DB_USER="root"
export BANK_DB_PASSWORD="your_password"

mvn compile
mvn exec:java -Dexec.args="--seed"
mvn exec:java
```

Run tests against a separate test database:

```bash
export BANK_DB_URL="jdbc:mysql://localhost:3306/bankdb_test"
mvn clean verify
```

## 🔮 Future Enhancements

- Spring Boot REST API
- HikariCP connection pooling
- Docker and Docker Compose
- GitHub Actions CI/CD
- Transaction limits and PDF account statements

## ⚠️ Disclaimer

This is a learning and portfolio project, not a production-ready banking system. Production deployment would require additional security controls, monitoring, session management, and operational safeguards.

## 👨‍💻 Skills Demonstrated

Java backend development, SQL, database design, ACID transactions, concurrency handling, authentication, authorization, automated testing, and query optimization.
