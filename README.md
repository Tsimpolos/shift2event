<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shift2Event</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            background-color: #f4f4f4;
            color: #333;
            padding: 20px;
        }
        h1, h2, h3 {
            color: #2c3e50;
        }
        .container {
            max-width: 800px;
            margin: auto;
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
        }
        .feature-list {
            list-style: none;
            padding: 0;
        }
        .feature-list li {
            background: #2ecc71;
            color: white;
            margin: 5px 0;
            padding: 10px;
            border-radius: 5px;
        }
        .code-block {
            background: #333;
            color: #fff;
            padding: 10px;
            border-radius: 5px;
            overflow-x: auto;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>🚀 Shift2Event</h1>
    <h2>Automate Employee Event Assignments Based on Shift Overlaps in Google Calendar</h2>
    
    <p>
        <strong>Shift2Event</strong> is a Google Apps Script that automatically assigns employees to events 
        based on their scheduled shifts. This eliminates the need for manual guest additions in Google Calendar 
        and ensures that employees are invited only when their shifts overlap with an event.
    </p>

    <h2>🚀 Features</h2>
    <ul class="feature-list">
        <li>✅ Automatically assigns employees to events when their shift overlaps with the event time.</li>
        <li>✅ Supports multiple employees working during the same shift.</li>
        <li>✅ Runs on a scheduled trigger (e.g., daily or hourly) to keep events updated.</li>
        <li>✅ Uses Google Apps Script, so no extra software is needed.</li>
    </ul>

    <h2>📌 How It Works</h2>
    <h3>Two Google Calendars</h3>
    <ul>
        <li><strong>Employee Shifts Calendar</strong> → Stores shift schedules of employees.</li>
        <li><strong>Company Events Calendar</strong> → Stores events where employees need to be assigned.</li>
    </ul>

    <h3>Automated Matching</h3>
    <p>
        The script scans both calen
