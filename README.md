# Jobs Dashboard (Power BI)

Report file: `Jobs_Dashboard.pbix`

## Overview
This report analyzes data job postings with a focus on job titles, salary medians, and posting trends. It includes a main dashboard and a drill-through page for a selected job title.

## Data model
Tables present:
- `job_postings_flat` (used in all report visuals)
- `funnel_data` (present in model, no visuals in report)
- `waterfall_data` (present in model, no visuals in report)

Key fields used in visuals:
- Job attributes: `job_title_short` (Job Title), `job_country` (Country), `job_schedule_type` (Job Type), `job_via` (Platform), `job_work_from_home` (Work from Home), `job_no_degree_mention` (No Degree Mention), `job_health_insurance` (Health Insurance)
- Dates: `job_posted_date` (Date Hierarchy: Year, Quarter, Month, Day)
- Salary: `salary_year_avg` (Yearly Salary), `salary_hour_avg` (Hourly Salary)

Measures and aggregations used:
- Job Count (count of `job_title_short`)
- Median Yearly Salary, Median Hourly Salary
- Average Yearly Salary, Average Hourly Salary
- Min Yearly Salary, Max Yearly Salary
- Min Hourly Salary, Max Hourly Salary
- Avg. Job Rating (measure)
- Job Trends (sparkline measure in the matrix)
- Percent of Jobs (measure for treemap)

## Pages and visuals
### Data Jobs Dashboard
- Scatter chart: Salary Median (USD) vs Hourly Median (USD) by Job Title.
- Matrix (pivot table): Job Title and `job_posted_date` Quarter with Job Count, Salary Median, Hourly Median, and Job Trends sparkline.
- Bar chart: Job Count by Job Title.
- Line chart: Job Count by `job_posted_date` (Year/Quarter/Month/Day hierarchy).
- Cards: Job Count, Median Yearly Salary, Median Hourly Salary, Avg. Job Rating.
- Slicer (dropdown): Job Title.
- Action button: "Drill Through to Job Title".
- Image button: home emoji used for page navigation.

### Job Title Drill Through
- Donut charts: Job Count by Work from Home, No Degree Mention, and Health Insurance.
- Gauges: Median vs Min/Max/Avg for Yearly Salary and Hourly Salary.
- Bar chart: Job Count by Platform.
- Treemap: Percent of Jobs by Job Type.
- Azure map: Job Count by Country with Median Yearly Salary in tooltip.
- Card: Job Title Drill Through (shows selected job title).
- Back button action icon.

Default drill-through filter on this page:
- Job Title = "Data Engineer" (overwritten when using drill-through from the main page).

## Interactions and navigation
- Job Title slicer drives page-level filtering on the main dashboard.
- Drill-through button navigates to the Job Title Drill Through page.
- Back button returns to the previous page.
- Bookmarks included: Column & Bar - Filtered, Column & Bar - Unfiltered, Column & Bar - Slicer, Column & Bar - No Slicer.

## Theme and visuals
- Base theme: CY24SU10.
- Custom visual package included: BoxWhiskerChart1455240051538 (not used in the current report visuals).

## Refresh and maintenance
- Open `Jobs_Dashboard.pbix` in Power BI Desktop and use Refresh.
- Data source connection details are not visible in the extracted report metadata; check Data source settings in Power BI Desktop when updating connections.
