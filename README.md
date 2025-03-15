# Student Attendance, Performance, and Certification Analysis Spreadsheet

This repository contains an Excel/spreadsheet solution designed to automate student management, attendance tracking, performance analysis, and certification processing. It demonstrates the application of spreadsheet software for data management and analysis, using formulas and functions to derive key metrics and insights.

## Table of Contents

-   [Project Overview](#project-overview)
-   [Data Analysis Skills Demonstrated](#data-analysis-skills-demonstrated)
-   [Data Structure](#data-structure)
-   [Worksheets](#worksheets)
-   [Usage](#usage)
-   [Formulas Explained](#formulas-explained)
    -   [Data Organization and "Filtering"](#data-organization-and-filtering)
    -   [Instructor Input in Course Tabs](#instructor-input-in-course-tabs)
    -   [Attendance Calculation](#attendance-calculation)
    -   [Performance Calculation](#performance-calculation)
    -   [Enrollment Calculation](#enrollment-calculation)
    -   [Data Retrieval and Certification in "StudentTracker"](#data-retrieval-and-certification-in-studenttracker)
-   [Conditional Formatting (Data Visualization)](#conditional-formatting-data-visualization)
-   [Contributing](#contributing)
-   [License](#license)
-   [Screenshots](#screenshots)

## Project Overview

This project showcases my data analysis development skills through the creation of a spreadsheet system for managing student information, tracking attendance, analyzing student performance, and certification processing. The initial development of this system was done using the online version of Microsoft 365. To ensure broader accessibility, cross-platform compatibility, and offline functionality, the project was further developed and finalized using LibreOffice Calc, which offers excellent compatibility and open-source support. The solution utilizes various functions and formulas to automate calculations, organize data, and derive key insights from student data.

## Data Analysis Skills Demonstrated

This project highlights the following data analysis skills:

-   **Data Organization and Structuring:** Designing a clear and efficient data structure using worksheets and columns to store different types of student information.
-   **Data Entry and Management:** Creating a system that facilitates data entry, editing, and organization.
-   **Data Filtering and Sorting:** Implementing a system to separate and organize student data by course.
-   **Data Cleaning and Validation:** (Implied through the use of consistent data entry formats and validation rules, though not explicitly shown in formulas).
-   **Data Calculation and Manipulation:** Using formulas and functions to calculate attendance percentages, overall grades, certification scores, and student rankings.
-   **Data Aggregation and Summarization:** Creating enrollment summaries and calculating the number of passed/failed learners per course.
-   **Data Lookup and Retrieval:** Using `XLOOKUP` to retrieve data from different worksheets and consolidate it in one place.
-   **Conditional Logic and Decision Making:** Using `IF` statements to assign grade classifications and determine certification outcomes.
-   **Data Visualization:** Applying conditional formatting to visually represent attendance status and highlight key data points.
-   **Data Interpretation:** Deriving insights from the calculated data, such as overall grades, certification status, and learner performance trends.
-   **Software Proficiency:** Demonstrating proficiency in both Microsoft 365 and LibreOffice Calc.

## Data Structure

The main student directory worksheet ("Students Directory") contains a tab named "StudentsEnroll" with the following columns:

-   **First Name:** The student's first name.
-   **Last Name:** The student's last name.
-   **Email:** The student's email address (used for communication).
-   **Class:** The name of the class the student is enrolled in (e.g., Maths1, Physics1, English Language). This column is crucial for organizing student data by course. Students are manually assigned to their respective course sheets (e.g., "Maths1," "Physics1," "English Language") based on the information in this column.
-   **Certification Status:** Displays the student's certification status, determined by the "Student Tracker," indicating whether the student has successfully earned a certificate.

The class-specific worksheets (e.g., "Maths1," "Physics1," "English Language") contain the following columns in addition to the student information:

-   **Week X Day Y:** Columns representing the days of the course (e.g., "Week 1 Day 1," "Week 1 Day 2," etc.) for attendance tracking.
-   **Week X Attendance:** Columns summarizing the weekly attendance percentage.
-   **Overall Attendance:** A column providing the overall attendance percentage.
-   **1st Test Score:** Records the student's score on the first test (0-100).
-   **2nd Test Score:** Records the student's score on the second test (0-100).
-   **Final Assignment Completion:** Indicates whether the student has completed the final assignment ("Yes" or "No").

The enrollment summary section (usually on the "StudentsEnroll" tab) includes:

-   **Course:** The name of the course.
-   **Learners:** The number of students enrolled in that course.
-   **Passed Learners:** The number of passed learners for each course.
-   **Failed Learners:** The number of failed learners for each course.

## Worksheets

The spreadsheet is organized into the following worksheets:

-   **Students Directory (main worksheet):**
    -   **StudentsEnroll (tab):** This tab contains the master list of all students and their class assignments, along with the enrollment summary. Student data is separated (or filtered) into course-specific sheets.
-   **Course-Specific Worksheets (e.g., Maths1, Physics1, English Language):**
    -   These sheets contain student data specific to each course.
    -   In some spreadsheet programs, a `FILTER` function (or similar functionality) might be used to automatically populate these sheets with the relevant students from the "StudentsEnroll" tab.
    -   Instructors use these sheets to record:
        -   Daily attendance
        -   1st test scores
        -   2nd test scores
        -   Final assignment completion status
    -   Formulas within these sheets calculate overall attendance.
-   **StudentTracker:** This sheet consolidates student data from different courses. `XLOOKUP` formulas are used to retrieve data from the course-specific sheets to calculate certification scores and rank students.

## Usage

1.  **Download:** Download the spreadsheet file (e.g., `student_enrollment.ods`).
2.  **Open:** Open the file in a spreadsheet program such as LibreOffice Calc, Microsoft Excel, Google Sheets, or similar. While developed and optimized for LibreOffice Calc, the spreadsheet is designed to be compatible with other common spreadsheet applications.
3.  **Add/Edit Data:**
    -   In the "StudentsEnroll" tab of the "Students Directory" sheet, add or edit student information, including their class assignment.
    -   In the course-specific worksheets (e.g., "Maths1"), you can add or track additional data relevant to that class, including attendance, test scores, and assignment completion.
4.  **View Results:** The spreadsheet will automatically calculate:
    -   Attendance percentages
    -   Final grades
    -   Certification status
    -   Enrollment summaries

## Formulas Explained

This section details the key formulas and data organization methods used in the spreadsheet:

###   Data Organization and "Filtering"

-   **Course-Specific Data Separation:**
    -   The spreadsheet uses a combination of data organization techniques to separate student data by course.
    -   The "Students Directory" worksheet contains a tab named "StudentsEnroll" with a "Class" column.
    -   **Filtering with `FILTER` (If Applicable):**
        -   In some spreadsheet programs that support it, the `FILTER` function (or similar functionality) might be used to automatically populate the course-specific worksheets with the correct students.
        -   For example, in the "Maths1" sheet, a formula like this could be used to pull the students from the "StudentsEnroll" sheet:
            ```excel
            =FILTER($StudendEnroll.A2:D44,$StudendEnroll.D2:D44=A1)
            ```
            -   `$StudendEnroll.A2:D44`:  The range of data in the "StudentsEnroll" sheet.
            -   `$StudendEnroll.D2:D44=A1`:  The criteria for filtering. It checks if the "Class" column in "StudentsEnroll" matches the course name (e.g., "Maths1") in cell `A1` of the current sheet.
            -   This formula would automatically display only the Maths1 students in the Maths1 sheet.
            -   This formula would automatically display only the Maths1 students in the Maths1 sheet.
        -   **Manual Filtering (Alternative):**
            -   If the `FILTER` function is not used, data for each student is manually entered into the worksheet corresponding to the course listed in the "Class" column.
        -   This ensures that each course-specific sheet contains only the relevant student data.

###   Instructor Input in Course Tabs

-   Instructors use the course-specific tabs to record student performance data:
    -   **Daily Attendance:** Attendance is marked for each student on each day.
    -   **1st Test Score:** The score for the first test is recorded.
    -   **2nd Test Score:** The score for the second test is recorded.
    -   **Final Assignment Completion:** The completion status ("Yes" or "No") of the final assignment is recorded.

###   Attendance Calculation

-   **Overall Attendance Percentage (in Course Tabs):**
    -   Formulas within the course-specific tabs calculate the overall attendance percentage for each student based on the daily attendance records.
    -   Example:
        ```excel
        =SUM(Week1_AttendanceCell:WeekN_AttendanceCell)/NumberOfWeeks
        ```
        -   `SUM`: Adds up the weekly attendance percentages.
        -   The sum is divided by the total number of weeks to get the average.

###   Performance Calculation

-   **Overall Grade Calculation (in "StudentTracker"):**

    ```excel
    =(E2*40)+F2*0.15+G2*0.2+(IF(H2="Yes",25,0))
    ```

    -   `E2`: Overall Attendance Percentage (weighted at 40%).
    -   `F2`: 1st Test Score (weighted at 15%).
    -   `G2`: 2nd Test Score (weighted at 20%).
    -   `H2`: Final Assignment Completion ("Yes" or "No"). If "Yes," 25 points are added.
    -   This formula calculates a weighted average of attendance, test scores, and assignment completion.

-   **Grade Classification (in "StudentTracker"):**

    ```excel
    =IF(I2>87,"Excellent",IF(I2<70,"Failed",IF(I2>77,"Good","Pass"))
    ```

    -   `I2`: Overall Grade.
    -   Nested `IF` statements assign a grade classification based on the overall grade.

###   Enrollment Calculation

-   **Learner Counts per Course (in "StudentsEnroll"):**

    ```excel
    =COUNTIF(D:D, "Maths1")
    ```

    -   `COUNTIF`: Counts the number of cells in column D (Class) that contain "Maths1" (or any other specific course).

-   **Passed Learners per Course (in "StudentsEnroll"):**

    ```excel
    =COUNTIFS(D2:D44,F2,E2:E44,"<>Failed")
    ```

    -   `COUNTIFS`: Counts the number of learners in a specific course who did not receive a "Failed" certification status.

-   **Failed Learners per Course (in "StudentsEnroll"):**

    ```excel
    =COUNTIFS(D2:D44,F2,E2:E44,"Failed")
    ```

    -   `COUNTIFS`: Counts the number of learners in a specific course who received a "Failed" certification status.

###   Data Retrieval and Certification in "StudentTracker"

-   **Data Retrieval with `XLOOKUP`:**
    -   The "StudentTracker" worksheet uses the `XLOOKUP` function to retrieve student data from the appropriate course-specific worksheets.
    -   For example, to retrieve a student's attendance:
        -   The `XLOOKUP` formula checks the student's class from the "StudentsEnroll" sheet.
        -   If the student is in "Maths1," the formula retrieves the attendance data from the "Maths1" worksheet.
        -   If the student is in "Physics1," the formula retrieves the attendance data from the "Physics1" worksheet, and so on.
        -   Example `XLOOKUP` Formula (Retrieving Attendance in "Student Tracker"):

        ```excel
        =IF(D2=$N$3,(XLOOKUP(C2,$'Physics1 DailyAttendance'.$D$2:$D$14,$'Physics1 DailyAttendance'.$R$2:$R$14)),XLOOKUP(C2,$'Maths1 DailyAttendance'.$D$2:$D$16,$'Maths1 DailyAttendance'.$R$2:$R$16,XLOOKUP(C2,$'English Language'.$D$2:$D$16,'English Language'.$R$2:$R$16)))
        ```

        -   `IF(D2=$N$3, ...)`: This part checks the student's class (in cell `D2`) against a reference cell (e.g., `$N$3` containing "Physics1").
        -   `XLOOKUP(C2,$'Physics1 DailyAttendance'.$D$2:$D$14,$'Physics1 DailyAttendance'.$R$2:$R$14)`: If the student is in "Physics1," this `XLOOKUP` retrieves the attendance from the "Physics1 DailyAttendance" sheet.
            -   `C2`: Student's identifier (e.g., email).
            -   `$'Physics1 DailyAttendance'.$D$2:$D$14`: Range of student identifiers in the "Physics1 DailyAttendance" sheet.
            -   `$'Physics1 DailyAttendance'.$R$2:$R$14`: Range of attendance data in the "Physics1 DailyAttendance" sheet.
        -   The nested `XLOOKUP` functions handle students in "Maths1" and "English Language" similarly, retrieving data from their respective sheets.
    -   **Certification Score and Rank Calculation:**
        -   Formulas within the "StudentTracker" worksheet use the retrieved data (attendance, test scores, assignment completion) to:
            -   Calculate a certification score for each student based on defined criteria (weighting).
            -   Calculate student rankings based on their certification scores.

## Conditional Formatting (Data Visualization)

Conditional formatting is used to visually represent data and highlight key information:

-   **Attendance Status:** Cells representing "P" (Present) are formatted with a green background, while cells containing "A" (Absent) are formatted with a red background. This provides a clear visual representation of student attendance.
-   **Low Attendance:** Cells containing attendance percentages below a certain threshold are formatted with a red background and white text. This highlights students with low attendance and allows for easy identification of students who may need additional support.

## Contributing

Contributions to this project are welcome! If you have suggestions for improvements, bug fixes, or new features, please:

1.  **Fork** the repository.
2.  **Create a new branch** for your changes.
3.  **Make your changes** and commit them.
4.  **Push** your changes to your fork.
5.  **Submit a pull request** to the original repository.

## License

This project is open source under the MIT License. See the `LICENSE` file for more information.

