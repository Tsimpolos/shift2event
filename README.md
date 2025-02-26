Shift2Event
🚀 Automate Employee Event Assignments Based on Shift Overlaps in Google Calendar

Shift2Event is a Google Apps Script that automatically assigns employees to events based on their scheduled shifts. This eliminates the need for manual guest additions in Google Calendar and ensures that employees are invited only when their shifts overlap with an event.

🚀 Features
✅ Automatically assigns employees to events when their shift overlaps with the event time.
✅ Supports multiple employees working during the same shift.
✅ Runs on a scheduled trigger (e.g., daily or hourly) to keep events updated.
✅ Uses Google Apps Script, so no extra software is needed.

📌 How It Works
Two Google Calendars

Employee Shifts Calendar → Stores shift schedules of employees.
Company Events Calendar → Stores events where employees need to be assigned.
Automated Matching

The script scans both calendars and identifies time overlaps between shifts and events.
Employees with shifts during an event's time slot are automatically added as guests.
Scheduled Execution

Set up a Google Apps Script trigger to run the automation at regular intervals.
🛠️ Installation & Setup
1️⃣ Get Your Calendar IDs
Go to Google Calendar.
Find the Employee Shifts Calendar and Company Events Calendar.
Click Settings & Sharing → Scroll down to Integrate Calendar → Copy the Calendar ID.
2️⃣ Set Up the Google Apps Script
Open Google Apps Script.
Create a new project and paste the following script:
