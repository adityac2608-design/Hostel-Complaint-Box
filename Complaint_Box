"""
Hostel Complaint Box System
A simple system for students to register complaints and administrators to manage them
"""
import datetime
import os

# File to store complaints
COMPLAINT_FILE = "complaints.txt"

# Complaint categories
CATEGORIES = {
    '1': 'Food Quality',
    '2': 'Room Maintenance',
    '3': 'Cleanliness',
    '4': 'Water Supply',
    '5': 'Electricity',
    '6': 'Internet/WiFi',
    '7': 'Security',
    '8': 'Other'
}
def clear_screen():
    """Clear the terminal screen"""
    os.system('cls' if os.name == 'nt' else 'clear')
def display_header():
    """Display the system header"""
    print("\n" + "=" * 60)
    print("           HOSTEL COMPLAINT BOX SYSTEM")
    print("=" * 60)
def display_main_menu():
    """Display main menu options"""
    print("\n1. Register New Complaint (Student)")
    print("2. View All Complaints (Admin)")
    print("3. Search Complaints")
    print("4. View Statistics")
    print("5. Exit")
    print("-" * 60)
def display_categories():
    """Display complaint categories"""
    print("\nComplaint Categories:")
    print("-" * 40)
    for key, value in CATEGORIES.items():
        print(f"{key}. {value}")
    print("-" * 40)
def register_complaint():
    """Register a new complaint"""
    clear_screen()
    display_header()
    print("\n REGISTER NEW COMPLAINT")
    print("-" * 60)

    # student details
    name = input("\nEnter your name: ").strip()
    if not name:
        print("Name cannot be empty!")
        input("\nPress Enter to continue...")
        return

    room_number=input("Enter your room number: ").strip()
    if not room_number:
        print("Room number cannot be empty!")
        input("\nPress Enter to continue...")
        return

    # Display and select category
    display_categories()
    category_choice = input("\nSelect complaint category (1-8): ").strip()

    if category_choice not in CATEGORIES:
        print("Invalid category selection!")
        input("\nPress Enter to continue...")
        return

    category = CATEGORIES[category_choice]

    # Get complaint description
    print("\nEnter your complaint (press Enter twice when done):")
    complaint_lines = []
    while True:
        line = input()
        if line == "":
            break
        complaint_lines.append(line)

    complaint = " ".join(complaint_lines)

    if not complaint:
        print("Complaint description cannot be empty!")
        input("\nPress Enter to continue...")
        return

    # Get priority
    print("\nPriority Level:")
    print("1. Low")
    print("2. Medium")
    print("3. High")
    priority_choice = input("Select priority (1-3): ").strip()

    priority_map = {'1': 'Low', '2': 'Medium', '3': 'High'}
    priority = priority_map.get(priority_choice, 'Medium')

    # Generate complaint ID
    complaint_id = generate_complaint_id()

    # Get current date and time
    timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")

    # Save complaint to file
    try:
        with open(COMPLAINT_FILE, 'a', encoding='utf-8') as file:
            file.write(f"\n{'=' * 60}\n")
            file.write(f"COMPLAINT ID: {complaint_id}\n")
            file.write(f"Date & Time: {timestamp}\n")
            file.write(f"Name: {name}\n")
            file.write(f"Room Number: {room_number}\n")
            file.write(f"Category: {category}\n")
            file.write(f"Priority: {priority}\n")
            file.write(f"Status: Pending\n")
            file.write(f"Complaint: {complaint}\n")
            file.write(f"{'='* 60}\n")

        print("\n Complaint registered successfully!")
        print(f"Your Complaint ID is: {complaint_id}")
        print("Please note this ID for future reference.")

    except Exception as e:
        print(f"\nError saving complaint: {str(e)}")

    input("\nPress Enter to continue...")


def generate_complaint_id():
    """Generate a unique complaint ID"""
    try:
        # Count existing complaints
        if not os.path.exists(COMPLAINT_FILE):
            return "C001"

        with open(COMPLAINT_FILE, 'r', encoding='utf-8') as file:
            content = file.read()
            count = content.count("COMPLAINT ID:")

        return f"C{str(count + 1).zfill(3)}"

    except:
        return "C001"

def view_all_complaints():
    """View all complaints (Admin function)"""
    clear_screen()
    display_header()
    print("\nALL COMPLAINTS")
    print("-" * 60)

    # Check if file exists
    if not os.path.exists(COMPLAINT_FILE):
        print("\n No complaints registered yet.")
        input("\nPress Enter to continue...")
        return

    try:
        with open(COMPLAINT_FILE, 'r', encoding='utf-8') as file:
            content = file.read()

            if not content.strip():
                print("\nNo complaints registered yet.")
            else:
                print(content)

    except Exception as e:
        print(f"\n Error reading complaints: {str(e)}")

    input("\nPress Enter to continue...")
def search_complaints():
    """Search complaints by ID, name, or room number"""
    clear_screen()
    display_header()
    print("\n SEARCH COMPLAINTS")
    print("-"*60)

    # Check if file exists
    if not os.path.exists(COMPLAINT_FILE):
        print("\n No complaints registered yet.")
        input("\nPress Enter to continue...")
        return

    print("\nSearch by:")
    print("1. Complaint ID")
    print("2. Student Name")
    print("3. Room Number")

    choice = input("\nEnter your choice (1-3): ").strip()
    search_term = input("Enter search term: ").strip().lower()

    if not search_term:
        print("Search term cannot be empty!")
        input("\nPress Enter to continue...")
        return
    try:
        with open(COMPLAINT_FILE, 'r', encoding='utf-8') as file:
            content = file.read()
            complaints = content.split("=" * 60)

            found = False
            for complaint in complaints:
                if not complaint.strip():
                    continue

                complaint_lower = complaint.lower()

                if choice == '1' and search_term in complaint_lower and 'complaint id' in complaint_lower:
                    print("=" * 60)
                    print(complaint)
                    print("=" * 60)
                    found = True
                elif choice == '2' and f"name: {search_term}" in complaint_lower:
                    print("=" * 60)
                    print(complaint)
                    print("=" * 60)
                    found = True
                elif choice == '3' and f"room number: {search_term}" in complaint_lower:
                    print("=" * 60)
                    print(complaint)
                    print("=" * 60)
                    found = True

            if not found:
                print("\n No complaints found matching your search.")

    except Exception as e:
        print(f"\nError searching complaints: {str(e)}")

    input("\nPress Enter to continue...")

def view_statistics():
    """Display complaint statistics"""
    clear_screen()
    display_header()
    print("\nCOMPLAINT STATISTICS")
    print("-"*60)

    # Check if file exists
    if not os.path.exists(COMPLAINT_FILE):
        print("\nNo complaints registered yet.")
        input("\nPress Enter to continue...")
        return

    try:
        with open(COMPLAINT_FILE, 'r', encoding='utf-8') as file:
            content = file.read()

            # Count total complaints
            total = content.count("COMPLAINT ID:")

            # Count by category
            category_counts = {}
            for category in CATEGORIES.values():
                count = content.count(f"Category: {category}")
                if count > 0:
                    category_counts[category] = count

            # Count by priority
            high_priority = content.count("Priority: High")
            medium_priority = content.count("Priority: Medium")
            low_priority = content.count("Priority: Low")

            # Count by status
            pending = content.count("Status: Pending")

            # Display statistics
            print(f"\nTotal Complaints: {total}")
            print("\nComplaints by Category:")
            for category, count in category_counts.items():
                print(f"   • {category}: {count}")

            print("\nComplaints by Priority:")
            print(f"   • High: {high_priority}")
            print(f"   • Medium: {medium_priority}")
            print(f"   • Low: {low_priority}")

            print("\n Complaint Status:")
            print(f"   • Pending: {pending}")

    except Exception as e:
        print(f"\n Error reading statistics: {str(e)}")

    input("\nPress Enter to continue...")

def main():
    """Main function to run the complaint system"""
    while True:
        clear_screen()
        display_header()
        display_main_menu()

        choice = input("\nEnter your choice (1-5): ").strip()

        if choice == '1':
            register_complaint()
        elif choice == '2':
            view_all_complaints()
        elif choice == '3':
            search_complaints()
        elif choice == '4':
            view_statistics()
        elif choice == '5':
            clear_screen()
            print("\n Thank you for using Hostel Complaint Box System!")
            break
        else:
            print("\n Invalid. Please select 1-5.")
            input("\nPress Enter to continue...")

# Run the program
if __name__== "__main__":
    try:
        main()
    except KeyboardInterrupt:
        print("\n\n⚠ Program interrupted. Goodbye!")
    except Exception as e:
        print(f"\n An unexpected error occurred: {str(e)}")
