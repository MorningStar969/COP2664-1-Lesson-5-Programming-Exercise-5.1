# COP2664-1-Lesson-5-Programming-Exercise-5.1
This is a GitHub repository link for Programming Exercise 5.1 of Module 5.

// This program is used to determine the average grade of a group of students by calculating the grade of one student and then adding it to the total grade.

import Foundation // Imports the Foundation library

var studentGrades: [String: Int] = ["Charlie": 85, "Alastor": 92, "Anthony": 78, "Baxter": 69] // Creates a dictionary of student names and grades
func addOrUpdateGrade(name: String, grade: Int) { // Creates a function that takes in a name and a grade and adds or updates the grade of the student in the dictionary.
    studentGrades[name] = grade
}
func removeStudent(name: String) { // Creates a function that takes in a name and removes the student from the dictionary.
    studentGrades.removeValue(forKey: name)
}
func printGrades() { // Creates a function that prints the grades of all students in the dictionary.
    for (name, grade) in studentGrades { // Iterates through the dictionary and prints the name and grade of each student.
        print("\(name): \(grade)")
    }
}
func getGrade(name: String) -> Int? { // Creates a function that takes in a name and returns the grade of the student if it exists in the dictionary.
    return studentGrades[name]
}
func calculateAverageGrade() -> Double { // Creates a function that calculates the average grade of all students in the dictionary and returns it.
    let total = studentGrades.values.reduce(0, +) // Reduces the values of the dictionary to a single value
    return Double(total) / Double(studentGrades.count) // Divides the total by the number of students to get the average grade
}
print("Enter a student's name to get their grade:")
if let name = readLine() { // Reads the user's input and stores it in a variable
    if let grade = getGrade(name: name) { // Calls the getGrade function to get the grade of the student.
        print("\(name)'s grade is \(grade)")
    }
}
print("Average grade of all students: \(calculateAverageGrade())") // Prints the average grade of all students
