🏠 Hostel Complaint Box System

A simple command-line application for managing hostel complaints. Students can register complaints and administrators can view, search, and analyze them.

 
 **Features:**

•Register complaints with unique IDs
•	8 complaint categories (Food, Maintenance, WiFi, etc.)
•	Priority levels (Low, Medium, High)
•	Search by ID, name, or room number
•	View statistics and analytics
•	No database required - uses text files
**Prerequisites:**
•	Python 3.6 or higher
•	No external libraries needed

 **Installation:**

1.	Download hostel_complaint_system.py
2.	Open terminal and navigate to the file location
3.	Run the program:
python hostel_complaint_system.py

**Main Menu Options:**

1.	Register New Complaint - Students submit complaints
2.	View All Complaints - Admins see all complaints
3.	Search Complaints - Search by ID, name, or room
4.	View Statistics - See complaint analytics
5.	Exit - Close the program

**Registering a Complaint:**

1.	Select option 1
2.	Enter your name and room number
3.	Choose complaint category (1-8)
4.	Write your complaint (press Enter twice when done)
5.	Set priority level (1-3)
6.	Note the Complaint ID provided

**Complaint Categories:**

1.	Food Quality
2.	Room Maintenance
3.	Cleanliness
4.	Water Supply
5.	Electricity
6.	Internet/WiFi
7.	Security
8.	Other
9.	 Files

•	hostel_complaint_system.py - Main program
•	complaints.txt - Auto-generated complaint storage

** Quick Tips:**

•	Students: Keep your Complaint ID for reference
•	Admins: Backup complaints.txt regularly
•	Priority: Use High only for urgent issues
•	Details: Write clear, detailed complaints
Example Output
============================================================
           HOSTEL COMPLAINT BOX SYSTEM
============================================================

1. Register New Complaint (Student)
2. View All Complaints (Admin)
3. Search Complaints
4. View Statistics
5. Exit
------------------------------------------------------------
Enter your choice (1-5): 1
📝 REGISTER NEW COMPLAINT
------------------------------------------------------------
Enter your name: John Doe
Enter your room number: A-101
Complaint Categories:
1. Food Quality
2. Room Maintenance
...
Select complaint category (1-8): 2
Enter your complaint (press Enter twice when done):
Ceiling fan not working properly

Priority Level:
1. Low  2. Medium  3. High
Select priority (1-3): 3
 Complaint registered successfully!
Your Complaint ID is: C001

** Future Enhancements:**

•	Email notifications
•	Complaint status updates (Resolved/In Progress)
•	Admin login system
•	Export complaints to CSV
•	Web-based interface

📝 License

Open source - Free to use and modify for educational purposes.


