# Summary of Amazon RDS Integration with Python App and GitHub Actions

This project demonstrates the integration of an Amazon RDS PostgreSQL instance with a Python application deployed using GitHub Actions. Below is an overview of the steps and functionality implemented:

---

## Steps Performed

### 1. Created an Amazon RDS Instance:
- Set up a PostgreSQL database instance on AWS RDS.
- Configured the security group to allow inbound traffic on port `5432` from trusted IPs for database access.

### 2. Database Setup:
- Connected to the RDS instance using Python's `psycopg2` library.
- Created a database named `test` inside the RDS instance.
- Created three tables:
  - **`test_table`**: Stores general test data.
  - **`test_table_2`**: Stores additional descriptive data.
  - **`test_table_3`**: Specifically created to store the developer's name (Muhammad Kashif).

### 3. Python Application:
- Developed a Python script to:
  - Connect to the RDS instance using environment variables (`DB_HOST`, `DB_NAME`, `DB_USER`, `DB_PASSWORD`).
  - Create tables in the database.
  - Insert test data into the tables.
  - Fetch and display the inserted data to confirm successful integration.

### 4. GitHub Actions Deployment:
- Configured GitHub Actions for automated deployment of the Python app.
- Stored the database credentials securely as GitHub Secrets.
- Verified the database connection and tested CRUD operations through automated workflows.

### 5. Data Insertions:
- Inserted data into the tables:
  - **`test_table`**: `"DevOps Class"`.
  - **`test_table_2`**: `"This is a test table 2"`.
  - **`test_table_3`**: `"Muhammad Kashif"`.

### 6. Verification:
- Fetched data from all tables to confirm successful insertions.
- Printed the retrieved data to the console for validation.

---

## Table Structure

### **`test_table`:**
```sql
CREATE TABLE test_table (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100)
);
```
### **`test_table`:**
```sql
CREATE TABLE test_table_2 (
    id SERIAL PRIMARY KEY,
    description VARCHAR(100)
);
```
### **`test_table`:**
```sql
CREATE TABLE test_table_3 (
    id SERIAL PRIMARY KEY,
    full_name VARCHAR(100)
);
```

### 7. GitHub Secrets Used:
- **`DB_HOST`**: The RDS endpoint.
- **`DB_NAME`**: The name of the database (e.g., `test`).
- **`DB_USER`**: The master username for the RDS instance.
- **`DB_PASSWORD`**: The password for the RDS instance.

---

### 8. Python Script Functionality
The Python script performs the following tasks:
1. **Connects to the RDS database** using `psycopg2`.
2. **Creates the required tables** if they do not exist.
3. **Inserts data** into the tables.
4. **Retrieves and prints the data** for verification.

---

### 9. Benefits of this Integration
- **Cloud-Based Database**: Utilizes Amazon RDS for reliable and scalable database management.
- **Automated Deployment**: GitHub Actions ensures consistent and repeatable deployments.
- **Secure Secrets Management**: Database credentials are securely stored in GitHub Secrets.

---

### 10. Future Enhancements
1. Add an **API layer** to interact with the database via HTTP.
2. Include **unit tests** in the GitHub Actions workflow.
3. Integrate more advanced features like **database migrations** using tools like Alembic.

