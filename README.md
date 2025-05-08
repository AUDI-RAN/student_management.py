class Student:
    def __init__(self, id, name, age):
        self.id = id
        self.name = name
        self.age = age

    def __str__(self):
        return f"ID: {self.id}, Name: {self.name}, Age: {self.age}"


class StudentManagementSystem:
    def __init__(self):
        self.students = []

    def add_student(self, student):
        self.students.append(student)
        print(f"Student {student.name} added successfully.")

    def remove_student(self, id):
        for student in self.students:
            if student.id == id:
                self.students.remove(student)
                print(f"Student with ID {id} removed successfully.")
                return
        print(f"Student with ID {id} not found.")

    def search_student(self, id):
        for student in self.students:
            if student.id == id:
                print(student)
                return
        print(f"Student with ID {id} not found.")

    def display_all_students(self):
        if not self.students:
            print("No students in the system.")
        else:
            for student in self.students:
                print(student)


if __name__ == "__main__":
    sms = StudentManagementSystem()

    while True:
        print("\nStudent Information Management System")
        print("1. Add Student")
        print("2. Remove Student")
        print("3. Search Student")
        print("4. Display All Students")
        print("5. Exit")
        choice = input("Enter your choice: ")

        if choice == "1":
            id = input("Enter student ID: ")
            name = input("Enter student name: ")
            age = input("Enter student age: ")
            student = Student(id, name, age)
            sms.add_student(student)
        elif choice == "2":
            id = input("Enter student ID to remove: ")
            sms.remove_student(id)
        elif choice == "3":
            id = input("Enter student ID to search: ")
            sms.search_student(id)
        elif choice == "4":
            sms.display_all_students()
        elif choice == "5":
            print("Exiting the system.")
            break
        else:
            print("Invalid choice. Please try again.")
    
