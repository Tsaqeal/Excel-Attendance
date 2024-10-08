# Student Attendance and Grade Calculation

This repository contains an Excel file designed to automate the calculation of student attendance and final grades based on attendance and various assignments. The formula for grade calculation is based on specific weightage allocated to each factor. 

## Features

- **Attendance Calculation**: Automatically calculates student attendance percentage.
- **Grade Calculation**: Calculates the final grade using the following weightage:
  - Attendance: 40%
  - Technical Assignment 1: 15%
  - Technical Assignment 2: 15%
  - Final Assignment: 30% (This will be applied only if marked "Yes"; otherwise, the weightage is 0%)

## File Overview

- **Student Directory.xlsx**: The main Excel file containing formulas for both attendance and grade calculation.

### Grade Calculation Formula

The final grade for each student is calculated using the following formula:


If the Final Assignment is marked as "No", its contribution to the grade will be zero.

## How to Use

1. Open the Student Directory.xlsx file.
2. Fill in the required fields for each student:
   - **Attendance**: Enter the attendance percentage for the student.
   - **Technical Assignment 1**: Enter the grade for the first technical assignment.
   - **Technical Assignment 2**: Enter the grade for the second technical assignment.
   - **Final Assignment**: Mark "Yes" if the student completed the final assignment or "No" if they did not.
3. The Excel file will automatically calculate:
   - **Attendance Percentage**
   - **Final Grade** based on the given weightage and the completion of the final assignment.

## Repository Structure


## License

This project is open source under the MIT License. See the [LICENSE](LICENSE) file for more information.

## Contributions

Feel free to open issues or submit pull requests if you want to improve the formulas or add additional features.

---

Enjoy automating your attendance and grade calculations!










