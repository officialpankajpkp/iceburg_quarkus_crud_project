#Test Cases - Podman, Trino, Iceberg, Quarkus, and GUI Integration

**Submitted By:**  Pankaj Kumar Pandey  
**Submitted To:** Mr. Vipin Tripathi  
**Test Case Version:**  1.0  
**Reviewer Name:** Mr. Vipin Tripathi  

## Goal

The objective of this project is to set up a complete data processing pipeline using Podman, Apache Iceberg, Trino, Java Quarkus, and a GUI-based application. The setup includes:

- Deploying Apache Iceberg inside a Podman container
- Installing and configuring Trino for querying Iceberg
- Writing Java Quarkus code to interact with Iceberg via Trino
- Building a GUI-based application for user interaction
- Ensuring proper data consistency, replication, and fault tolerance

## Test Cases

### 1. Environment Setup Tests

**Test Case 1.1 – Verify Podman installation**  
**Scenario:** Ensure Podman is installed correctly.  
**Remark:** Verify Podman version after installation.  
**Given:** A system with Podman installed.  
**When:** The command `podman --version` is executed.  
**Then:** The Podman version should be displayed.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  

**Test Case 1.2 – Verify Iceberg installation inside Podman**  
**Scenario:** Validate Iceberg service deployment.  
**Remark:** Ensure Iceberg starts without errors.  
**Given:** Iceberg is deployed inside a Podman container.  
**When:** The container logs are checked.  
**Then:** Iceberg service should start without errors.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  

**Test Case 1.3 – Verify Trino installation**  
**Scenario:** Confirm Trino installation and connection.  
**Remark:** Trino should list Iceberg as a catalog.  
**Given:** Trino is running inside a container.  
**When:** The query `SHOW CATALOGS;` is executed.  
**Then:** The Iceberg catalog should be listed.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  

**Test Case 1.4 – Check connectivity between Trino and Iceberg**  
**Scenario:** Ensure Trino can query Iceberg tables.  
**Remark:** Trino should execute queries successfully.  
**Given:** A Trino instance connected to Iceberg.  
**When:** The query `SELECT * FROM iceberg.default.test_table LIMIT 1;` is run.  
**Then:** The query should execute successfully.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  

### 2. Database Operations (Trino + Iceberg)

**Test Case 2.1 – Create an Iceberg Table**  
**Scenario:** Validate table creation in Iceberg.  
**Remark:** Ensure table creation completes without errors.  
**Given:** A running Iceberg instance.  
**When:** The query `CREATE TABLE iceberg.default.users (id INT, name STRING);` is executed.  
**Then:** The table should be created successfully.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  

**Test Case 2.2 – Insert Data into Iceberg Table**  
**Scenario:** Verify data insertion into Iceberg.  
**Remark:** Ensure data is stored correctly.  
**Given:** A created Iceberg table.  
**When:** The query `INSERT INTO iceberg.default.users VALUES (1, 'Alice');` is executed.  
**Then:** The data should be inserted without errors.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  

**Test Case 2.3 – Retrieve Data from Iceberg Table**  
**Scenario:** Verify data retrieval.  
**Remark:** Ensure correct data is fetched.  
**Given:** An Iceberg table with data.  
**When:** The query `SELECT * FROM iceberg.default.users;` is executed.  
**Then:** The correct data should be retrieved.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  



**Test Case 2.4 – Update an Iceberg Table Record**  
**Scenario:** Validate record update in Iceberg.  
**Remark:** Iceberg may not support direct updates; verify alternative approaches.  
**Given:** An existing table `iceberg.default.users` with records.  
**When:** The query `UPDATE iceberg.default.users SET name = 'Bob' WHERE id = 1;` is executed.  
**Then:** The record should be updated successfully, or an alternative approach should be used.  
**Test Run Date:** _(To be filled)_  
**Result:** Pending/Pass/Fail  



**Test Case 2.5 – Delete Data from Iceberg Table**  
**Scenario:** Validate data deletion in Iceberg.  
**Remark:** Ensure data deletion completes without errors.  
**Given:** A record exists in the `iceberg.default.users` table.  
**When:** The query `DELETE FROM iceberg.default.users WHERE id = 1;` is executed.  
**Then:** The data should be deleted successfully.  
**Test Run Date:** _(To be filled)_  
**Result:** Pending/Pass/Fail  



**Test Case 2.6 – Validate Schema Evolution**  
**Scenario:** Validate the addition of a new column in Iceberg table.  
**Remark:** Ensure the schema evolves correctly without errors.  
**Given:** A created Iceberg table.  
**When:** The query `ALTER TABLE iceberg.default.users ADD COLUMN age INT;` is executed.  
**Then:** The column `age` should be added successfully to the table.  
**Test Run Date:** _(To be filled)_  
**Result:** Pending/Pass/Fail  



### 3. Java Quarkus Integration Tests

**Test Case 3.1 – Connect Quarkus App to Trino**  
**Scenario:** Validate Trino connection in Quarkus.  
**Remark:** Ensure Quarkus can run queries.  
**Given:** A running Quarkus app.  
**When:** The app executes `SELECT 1`.  
**Then:** The connection should be successful.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  

**Test Case 3.2 – Fetch Data from Iceberg via GUI**  
**Scenario:** Ensure the GUI retrieves data correctly.  
**Remark:** GUI should fetch and display data.  
**Given:** A running GUI and Iceberg table.  
**When:** The user runs a query from the GUI.  
**Then:** Data should be displayed correctly.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail 

**Test Case 3.3 – Insert Data via GUI**  
**Scenario:** Validate data insertion via GUI.  
**Remark:** Ensure data is stored correctly in Iceberg.  
**Given:** A running GUI form for inserting data.  
**When:** A user with id=2 and name='Charlie' is inserted through the GUI.  
**Then:** The data should be stored in Iceberg without errors.  
**Test Run Date:** _(To be filled)_  
**Result:** Pending/Pass/Fail  

---

**Test Case 3.4 – Update Data via GUI**  
**Scenario:** Validate data update via GUI.  
**Remark:** Ensure data is updated correctly in Iceberg.  
**Given:** A running GUI form with editable user data.  
**When:** A user’s name is edited via the GUI and saved.  
**Then:** The data should be updated correctly in Iceberg.  
**Test Run Date:** _(To be filled)_  
**Result:** Pending/Pass/Fail  

---

**Test Case 3.5 – Delete Data via GUI**  
**Scenario:** Validate data deletion via GUI.  
**Remark:** Ensure data is removed correctly from Iceberg.  
**Given:** A running GUI with user data to delete.  
**When:** A record is deleted from the GUI.  
**Then:** The record should be removed from Iceberg.  
**Test Run Date:** _(To be filled)_  
**Result:** Pending/Pass/Fail  

---

**Test Case 3.6 – Handle Large Data Insertions**  
**Scenario:** Validate handling of large data insertions via GUI.  
**Remark:** Ensure the system can handle large volumes of data without errors.  
**Given:** A running GUI form capable of inserting large amounts of data.  
**When:** 10,000+ rows are inserted from the GUI.  
**Then:** The system should handle the insertion efficiently without errors.  
**Test Run Date:** _(To be filled)_  
**Result:** Pending/Pass/Fail  

---

### 4. Performance & Security Tests

**Test Case 4.1 – Query Performance for Large Data**  
**Scenario:** Measure query performance on large datasets.  
**Remark:** Ensure acceptable execution times.  
**Given:** A table with 1 million records.  
**When:** The query `SELECT * FROM iceberg.default.users;` is executed.  
**Then:** The query should execute within an acceptable range.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  

**Test Case 4.2 – Unauthorized Access Handling**  
**Scenario:** Ensure security mechanisms prevent unauthorized access.  
**Remark:** System should enforce authentication.  
**Given:** A Trino/Iceberg instance.  
**When:** An unauthorized user attempts access.  
**Then:** Access should be denied.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  

**Test Case 4.3 – Test Failure Recovery**  
**Scenario:** Validate system behavior after failure.  
**Remark:** Ensure data consistency post-restart.  
**Given:** A running system.  
**When:** Iceberg or Trino is restarted.  
**Then:** Queries should execute without data loss.  
**Test Run Date:**  
**Result:** Pending/Pass/Fail  
