# ==========================================================
                                                        # Student Document Request Monitoring System
                                                           # PHINMA Cagayan de Oro College
                                                 # ==========================================================


                   #==========================================================FINAL CODE==========================================================



admin_username = "admin"
admin_password = "admin123"

                                                  #==================== Student Accounts already exist ====================
students = {
    "jay": {
        "password": "jay123",
        "student_id": "126519120056",
        "gender": "Male"
    }
}

document_requests = {}
request_number = 1001


                                                      # ==================== Admin Login ====================

def admin_login():
    print("=================== Admin Login ===================")
    username = input("Enter username: ")
    password = input("Enter password: ")

    if username == admin_username and password == admin_password:
        print("Admin Login Successful.")
        admin_menu()
    else:
        print("Invalid admin credentials.")


                                                       # ==================== Admin Menu ====================

def admin_menu():
    while True:
        print("=================== Admin Menu ===================")
        print("1. View document requests")
        print("2. Update request status")
        print("3. View student accounts")
        print("4. View request records")
        print("5. Back to Main Menu")
        print("6. Logout")

        choice = input("Enter choice: ")

                                               #==================== admin can View document requests ====================
        if choice == "1":
            if not document_requests:
                print("No document requests yet.")
            else:
                print("========== Student Document Requests ==========")
                print("Request No. | Student | Student ID | Gender | Document | Price | Status")
                print("-" * 100)

                for number, info in document_requests.items():
                    print(
                        number, "|",
                        info["username"], "|",
                        info["student_id"], "|",
                        info["gender"], "|",
                        info["document"], "|",
                        ""+ str(info["price"]), "|",
                        info["status"]
                    )

                                               # ==================== admin can view Update request status ====================
        elif choice == "2":
            if not document_requests:
                print("No document requests available to update.")
                continue

            print("Available Request Numbers:")

            for number in document_requests:
                print(number, end=" ")

            print()
            request_no = input("Enter request number: ")

            if request_no not in document_requests:
                print("Request number not found.")
                continue

            print("Status Options:")
            print("1. Pending")
            print("2. Processing")
            print("3. Ready for Claiming")
            print("4. Completed")

            status_choice = input("Enter choice: ")

            if status_choice == "1":
                new_status = "Pending"
            elif status_choice == "2":
                new_status = "Processing"
            elif status_choice == "3":
                new_status = "Ready for Claiming"
            elif status_choice == "4":
                new_status = "Completed"
            else:
                print("Invalid status choice.")
                continue

            confirm = input(
                "Confirm status update? (yes/no): "
            ).lower()

            if confirm == "yes":
                document_requests[request_no]["status"] = new_status
                print("Request status updated successfully.")
            else:
                print("Status update cancelled.")

                                                   #==================== admin can View student accounts ====================
        elif choice == "3":
            if not students:
                print("No student accounts yet.")
            else:
                print("================ Student Accounts ================")

                for username, info in students.items():
                    print(f"Username: {username}")
                    print(f"School ID: {info['student_id']}")
                    print(f"Gender: {info['gender']}")
                    print("==================================================")

                                                #==================== admin can View request records ====================
        elif choice == "4":
            if not document_requests:
                print("No request records yet.")
            else:
                print("================ Request Records ================")
                print("Request No. | Student | Student ID | Gender | Document | Price | Status")
                print("-" * 100)

                for number, info in document_requests.items():
                    print(
                        number, "|",
                        info["username"], "|",
                        info["student_id"], "|",
                        info["gender"], "|",
                        info["document"], "|",
                        ""+ str(info["price"]), "|",
                        info["status"]
                    )
        elif choice == "5":
            print("Returning to Main Menu...")
            break

        elif choice == "6":
            print("Admin logged out successfully.")
            break

        else:
            print("Invalid choice. Please try again.")


                                                   # ==================== Student Account ====================

def student_login():
    while True:
        print("================ Student Account Menu ================")
        print("1. Create Account")
        print("2. Login")
        print("3. Back to Main Menu")

        choice = input("Enter choice: ")

                                                  # ==================== Create student account ====================

        if choice == "1":
            username = input("Create username: ").strip()

            if not username:
                print("Username cannot be empty.")
                continue

            if username in students:
                print("Username is already registered.")
                continue

            student_id = input("Enter School ID: ").strip()

            if not student_id:
                print("School ID cannot be empty.")
                continue

                                                  # ==================== Check duplicate School ID ====================
            id_exists = False

            for info in students.values():
                if info["student_id"] == student_id:
                    id_exists = True
                    break

            if id_exists:
                print("School ID is already registered.")
                continue

            gender = input("Enter gender (Male/Female): ").strip().capitalize()

            if gender != "Male" and gender != "Female":
                print("Invalid gender. Please enter Male or Female.")
                continue

            password = input("Create password: ")

            if not password:
                print("Password cannot be empty.")
                continue

            confirm_password = input("Confirm password: ")

            if password != confirm_password:
                print("Passwords do not match.")
                continue

            students[username] = {
                "password": password,
                "student_id": student_id,
                "gender": gender
            }

            print("Account created successfully!")
            print(f"Username: {username}")
            print(f"School ID: {student_id}")
            print(f"Gender: {gender}")

                                                          #==================== Student login ====================
        elif choice == "2":
            username = input("Enter username: ").strip()
            password = input("Enter password: ")

            if (
                username in students
                and students[username]["password"] == password
            ):
                print("Student Login Successful!")
                student_menu(username)
            else:
                print("Invalid username or password.")

        elif choice == "3":
            print("Returning to Main Menu...")
            break

        else:
            print("Invalid choice. Please try again.")


                                                         # ==================== Student Menu ====================

def student_menu(username):
    global request_number

    documents = {
        "1": ("Transcript of Records", 150),
        "2": ("Certificate of Enrollment", 100),
        "3": ("Certificate of Good Moral Character", 100),
        "4": ("Certificate of Graduation", 150),
        "5": ("Clearance", 50),
        "6": ("Certificate of Completion", 100),
        "7": ("Diploma", 200),
        "8": ("Certificate of Transfer Credentials", 150),
        "9": ("Certificate of Enrollment History", 100),
        "10": ("Certificate of Honorable Dismissal", 150)
    }
    while True:
        print(f"================ Student Menu ({username}) ================")
        print("1. Request a document")
        print("2. View my requests")
        print("3. View request history")
        print("4. Logout")
        print("5. Back")

        choice = input("Enter choice: ")

        if choice == "5":
            print("Returning to Main Menu...")
            break
                                                       # ==================== student can Request a document ====================
        if choice == "1":
            while True:
                print("========== DOCUMENT PRICE LIST ==========")
                print("+------+--------------------------------------+----------+")
                print(f"| {'No.':<4} | {'Document Type':<36} | {'Price':<8} |")
                print("+------+--------------------------------------+----------+")

                for number, info in documents.items():
                    print(
                        f"| {number:<4} | {info[0]:<36} | "
                        f"P{info[1]:<7} |"
                    )

                print("+------+--------------------------------------+----------+")
                print("11. Back")

                document_choice = input("Enter document number: ")

                if document_choice == "11":
                    break

                if document_choice not in documents:
                    print("Invalid choice! Please try again.")
                    continue

                document, price = documents[document_choice]

                                                 # ==================== Get student information ====================
                account_info = students[username]
                student_id = account_info["student_id"]
                gender = account_info["gender"]
 
                print("========== Confirm Document Request ==========")
                print("-----------------------------------------------")
                print("Student    :", username)
                print("School ID  :", student_id)
                print("Gender     :", gender)
                print("Document   :", document)
                print("Price      : P", price, sep="")
                print("-----------------------------------------------")

                confirm = input("Submit this request? (yes/no): ").lower()

                if confirm != "yes":
                   print("Document request cancelled.")
                   continue

                                         # ==================== Create or generate a document request ====================
                request_no = str(request_number)
                request_number += 1

                document_requests[request_no] = {
                    "username": username,
                    "student_id": student_id,
                    "gender": gender,
                    "document": document,
                    "price": price,
                    "status": "Pending"
                }
                print("========== DOCUMENT REQUEST ==========")
                print("Request No. | Username | School ID | Gender | Document | Price | Status")
                print("-" * 80)
                print(request_no, "|", username, "|", student_id, "|", gender, "|", document, "| ", price, "| Pending")
                print("Request submitted successfully!")

                                              # ==================== student can View current request s====================
        elif choice == "2":
            found = False

            print("====================== My Document Requests ======================")
            print("+------------+----------------------+--------------------------------------+----------+----------------------+")
            print(f"| {'Request No.':<10} | {'Student ID':<20} | {'Document':<36} | {'Price':<8} | {'Status':<20} |")
            print("+------------+----------------------+--------------------------------------+----------+----------------------+")

            for number, info in document_requests.items():
                if info["username"] == username:
                    print(
                        f"| {number:<10} | "
                        f"{info['student_id']:<20} | "
                        f"{info['document']:<36} | "
                        f"P{info['price']:<7} | "
                        f"{info['status']:<20} |"
                    )
                    found = True

            print("+------------+----------------------+--------------------------------------+----------+----------------------+")

            if not found:
                print("You have no document requests yet.")

                                               #==================== student can View request history ====================
        elif choice == "3":
            found = False

            print("========== Request History ==========")
            print("Request No. | Student ID | Gender | Document | Price | Status")
            print("-" * 80)

            for number, info in document_requests.items():
                if info["username"] == username:
                    print(
                    number, "|",
                    info["student_id"], "|",
                    info["gender"], "|",
                    info["document"], "|",
                    ""+ str(info["price"]), "|",
                    info["status"]
                )
                found = True

            if not found:
                print("No request history yet.")


                                                         #==================== Logout ====================
        elif choice == "4":
            print("Student logged out successfully.")
            break

        else:
            print("Invalid choice. Please try again.")


                                                        # ==================== Main Menu ====================

def main():
    while True:
        print("==============================================")
        print("Student Document Request Monitoring System in")
        print("PHINMA Cagayan de Oro College")
        print("==============================================")
        print("1. Admin Login")
        print("2. Student login")
        print("3. Exit")

        choice = input("Enter choice: ")

        if choice == "1":
            admin_login()

        elif choice == "2":
            student_login()

        elif choice == "3":
            confirm = input(
                "Are you sure you want to exit? (yes/no): "
            ).lower()

            if confirm == "yes":
                print("Thank you for using the system!")
                break

            elif confirm == "no":
                print("Returning to Main Menu...")

            else:
                print("Invalid choice. Returning to Main Menu.")

        else:
            print("Invalid choice. Please try again.")

main()
