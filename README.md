# Student Enrollment Dashboard | Looker Studio

## Project Overview

The **Student Enrollment Dashboard** is a data visualization project built with Google Looker Studio using student enrollment data stored in Microsoft Excel. It helps explore enrollment patterns, student demographics, attendance, scholarships, and placement outcomes through interactive charts and filters.

> **Project status:** Add a published Looker Studio report link and dashboard screenshots when available.
>  Live Link: https://datastudio.google.com/reporting/c5aca044-0da2-4632-82da-ac80f9f19f7c

## Objectives

- Monitor total and active student enrollment.
- Analyze enrollment by course, department, year, and status.
- Explore student attendance and ratings.
- Summarize scholarships and fee-related information.
- Review placement status and placement salary.
- Explore student locations using geographic fields, where supported.

## Dataset

The source workbook is `student_enrollment_lookerstudio_dataset.xlsx`.

The main student-level worksheet is **`Sheet1`**. Use this worksheet as the primary data source rather than combining it with summary worksheets, which could lead to double-counting.

### Key Fields

| Category | Fields |
|---|---|
| Student profile | `Student_ID`, `Student_Name`, `Gender`, `Age` |
| Course details | `Course`, `Department` |
| Location | `City`, `State`, `Country`, `Latitude`, `Longitude` |
| Enrollment | `Admission_Year`, `Admission_Date`, `Enrollment_Status` |
| Financials | `Annual_Fees`, `Scholarship`, `Scholarship_Amount` |
| Attendance and outcomes | `Attendance_Percentage`, `Placement_Status`, `Placement_Salary`, `Student_Rating` |

The current workbook contains 50 student records and 21 fields in the main worksheet. Recheck these counts if the source data changes.

## Tools and Technologies

- Microsoft Excel — source dataset
- Google Sheets — data preparation and connector
- Google Looker Studio — interactive dashboard
- GitHub — project documentation and version control

## Dashboard Features

### KPI Scorecards
- Total Students
- Active Students
- Average Attendance
- Placed Students

### Charts
- Students by Course — bar chart
- Enrollment Status — pie/donut chart
- Admissions by Year — column chart
- Placement Outcomes — pie/donut chart
- Scholarship Distribution by Course — bar chart
- Average Placement Salary by Course — bar chart

### Interactive Filters
- Course
- Gender
- Admission Year
- Enrollment Status
- Placement Status
- Scholarship

### Geographic Analysis
The dataset includes city, state, country, latitude, and longitude fields. A map can be added when geographic fields are configured correctly and supported by the selected Looker Studio chart.

## Setup Instructions

1. Open the Excel workbook.
2. Check `Sheet1` for column headers, data types, missing values, and duplicate student IDs.
3. Upload the workbook to Google Drive and open it in Google Sheets, or import it into an existing Google Sheet.
4. Open [Google Looker Studio](https://lookerstudio.google.com/).
5. Create a report and add the **Google Sheets** connector.
6. Select the spreadsheet and the `Sheet1` worksheet.
7. Verify field types, especially dates, numeric values, percentages, and geographic fields.
8. Add scorecards, charts, and filter controls using the dashboard features listed above.
9. Validate chart totals against the source data.
10. Share the report with appropriate permissions and add its URL to the Project Links section below.

## Data Quality Notes

- Confirm `Student_ID` is unique before using a distinct count.
- Ensure `Admission_Date` is recognized as a date.
- Keep fees, scholarship amounts, and placement salaries numeric.
- Check how `Attendance_Percentage` is stored before formatting it as a percentage. Values on a 0–100 scale should not accidentally be multiplied by 100 in the display.
- For salary analysis, filter to `Placement_Status = Placed` if calculating average salary among placed students only.
- Geographic charts may require fields to be assigned the correct geographic type.
- Use only the student-level worksheet for student counts; avoid counting summary rows as student records.

## Sample Validation Checks

Use these figures to validate the current source workbook. Recheck them if the dataset is updated:

- Total student records: **50**
- Active students: **37**
- Completed students: **11**
- Dropped students: **2**
- Placed students: **22**
- Average attendance: approximately **80.45%**

## Project Links

- **Looker Studio Dashboard:** _Add your published report URL here_
- **Dataset:** _Add a repository-relative path or a link to the dataset, if you are permitted to share it_
- **Dashboard Screenshot:** _Add a screenshot path, for example `images/dashboard-overview.png`_

## Suggested Repository Structure

```text
student-enrollment-dashboard/
├── README.md
├── student_enrollment_lookerstudio_dataset.xlsx
└── images/
    └── dashboard-overview.png
```

Adjust file names and structure to match the files actually committed to your repository.

## Privacy and Sharing

The dataset includes student-related information. Before uploading it to a public GitHub repository, remove or anonymize names, IDs, precise locations, and any other personal or sensitive information unless you have explicit permission to publish them. Consider sharing a synthetic or anonymized sample dataset instead.

## Future Improvements

- Add a placement rate KPI with a clearly defined eligible-student denominator.
- Add year-over-year enrollment comparisons.
- Add course and department comparisons.
- Improve geographic visualization and validate location coverage.
- Document calculated fields and dashboard filters.


