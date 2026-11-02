# Student Document Request Monitoring System

A console-based document request and tracking system designed for **PHINMA Cagayan de Oro College**.  
This Python application allows students to request official school documents online while providing administrators with tools to update request statuses, view records, and manage student accounts.

Features

Main Menu

* Admin Login — Access administrative control panel
* Student Login — Account creation, login, and request portal
* Exit System — Safely closes the application with confirmation

Admin Menu

1. View Document Requests — Displays all submitted document requests
2. Update Request Status — Modify request status (Pending, Processing, Ready for Claiming, Completed)
3. View Student Accounts — Display registered student credentials and details
4. View Request Records — Access detailed log history of document transactions
5. Back to Main Menu
6. Logout

Student Menu

1. Request a Document — Select from available documents with automated pricing computation
2. View My Requests — Track current status of submitted document requests
3. View Request History — Review overall transaction history
4. Logout
5. Back

Document Price List

Document Type | Price
--- | ---
Transcript of Records | P150
Certificate of Enrollment | P100
Certificate of Good Moral Character | P100
Certificate of Graduation | P150
Clearance | P50
Certificate of Completion | P100
Diploma | P200
Certificate of Transfer Credentials | P150
Certificate of Enrollment History | P100
Certificate of Honorable Dismissal | P150

Default System Credentials

### Admin Account
* **Username:** `admin`
* **Password:** `admin123`

### Pre-registered Student Account
Username | Password | School ID | Gender
--- | --- | --- | ---
jay | jay123 | 126519120056 | Male

How to Run

1. Make sure you have Python 3 installed.
2. Save the code as a `.py` file (e.g. `document_system.py`).
3. Run it in your terminal / command prompt:

```bash
python document_system.py

or

python3 document_system.py

Key Behaviors

1. Account Validation: Checks for duplicate usernames and unique School IDs during account creation.
2. Automated Request Numbering: Generates sequential tracking numbers starting from 1001.
3. Real-time Status Updates: Admins can seamlessly switch request states between Pending, Processing, Ready for Claiming, and Completed.
4. Structured Console Tables: Formatted console outputs for clear visualization of price lists, student registries, and request history.

Project Structure (Single File)
All data is stored in memory using native Python dictionaries and nested records:

1. students — Account data store containing passwords, student IDs, and gender details
2. document_requests — Transaction records indexed by request numbers
3. documents — Lookup dictionary for document types and standard pricing

No external libraries or database setup required — pure Python standard execution.
Notes

1. In-Memory Storage: Data resets when the application terminates.
2. Command-Line Interface: Text-based console interaction.
3. Intended for academic project demonstrations and workflow simulations.

Author

Developed for PHINMA Cagayan de Oro College student project demonstration.
Feel free to contribute, fork, or enhance (add database persistence, desktop UI, etc.).
