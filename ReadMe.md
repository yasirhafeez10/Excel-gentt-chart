# Gantt Chart - Excel Source

**Repository file:** `107b09a5-ff47-4e3f-8509-bf791dc474cb.xlsx`  
**Primary sheet:** `Sheet1`

## Overview
This repository contains an Excel workbook that holds task/date data suitable for creating a **Gantt chart** in Excel or other spreadsheet software. The sheet `Sheet1` includes the task names, start and end dates, and a precomputed date difference (duration in days).

## Data preview (first rows)
| Names  | Start Date | End Date   | Date diff (days) |
|--------|------------|------------|------------------:|
| Yasir  | 2025-10-05 | 2025-10-05 |                 0 |
| Ali    | 2025-10-07 | 2025-10-20 |                13 |
| Zain   | 2025-01-10 | 2025-11-30 |               324 |
| Kashif | 2025-11-01 | 2025-11-01 |                 0 |
| Sameer | 2025-11-15 | 2027-01-17 |               428 |
| Fizan  | 2025-05-01 | 2025-12-01 |               214 |
| Mehran | 2025-12-25 | 2026-12-25 |               365 |
| Talib  | 2026-01-10 | 2026-12-01 |               325 |

## Columns explained
- **Names** — The task, person, or item label for the Gantt row.  
- **Start Date** — Task start date (`YYYY-MM-DD`).  
- **End Date** — Task end date (`YYYY-MM-DD`).  
- **Date diff** — Duration in days (End Date - Start Date). This column can be recalculated using Excel formulas if needed.

### Formula to compute `Date diff`
If `Start Date` is in column B and `End Date` in column C (row 2), use:
```excel
=MAX(0, C2 - B2)
```
and format as a number.

## How to create a Gantt chart in Excel (quick steps)
1. Open the workbook in Excel (or LibreOffice Calc / Google Sheets).  
2. Make sure `Start Date` and `End Date` are proper date types (not text).  
3. Add a helper column **Start (numeric)** that converts the start date to Excel serial number (optional): `=B2` (ensure cell format is Date for B column).  
4. Select the range which includes `Names`, `Start Date` (or Start numeric), and `Date diff`.  
5. Insert → Chart → **Stacked Bar Chart**.  
6. In the chart, make the series order: *Start Date (hidden)* then *Duration (Date diff)*.  
7. Format the Start Date series to have **no fill** so only durations (Gantt bars) are visible.  
8. Reverse the vertical axis so the first task appears at top: Axis Options → Categories in reverse order.  
9. Adjust date axis (horizontal) minimum/maximum as needed (Axis Options → Bounds).  
10. Apply colors/conditional formatting to show progress, milestones, or owners.

## How to create a Gantt-like chart in Google Sheets
- Use the same approach: create a stacked bar chart with `Start` and `Duration` series, then make the Start series transparent.

## Notes & tips
- Make a backup before editing the original file.  
- If `Date diff` is missing or incorrect, recalculate using the formula in the section above.  
- For multi-year projects, adjust the horizontal axis to show months/years.  
- To show progress, add a `Completed` column and stack it within the Duration series or use colored overlays.

## Suggested improvements (if you want to update the workbook)
- Add `Progress (%)` column to visually indicate completion.  
- Add `Dependencies` column to track task relationships.  
- Add `Priority` or `Category` for color grouping.  
- Convert `Start Date`/`End Date` to consistent ISO format (`YYYY-MM-DD`) to avoid locale issues.

## License
You can add a LICENSE file of your choice. If you don't choose, assume contents are **unlicensed** and not ready for public distribution.

## Contact / Author
If you want me to:
- generate the Gantt chart image from this data,
- create a preformatted Excel Gantt sheet,
- or produce a PNG/SVG of the chart for the repo README,

tell me which option and I'll create the file for you.

