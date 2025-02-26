# 🚀 Shift2Event  
**Automate Employee Event Assignments Based on Shift Overlaps in Google Calendar**  

Shift2Event is a Google Apps Script that **automatically assigns employees to events** based on their scheduled shifts.  
This eliminates the need for **manual guest additions** in Google Calendar and ensures that employees are invited **only when their shifts overlap** with an event.  

---

## 🚀 Features  
✅ **Automatically assigns employees** to events when their shift overlaps with the event time.  
✅ **Supports multiple employees** working during the same shift.  
✅ **Runs on a scheduled trigger** (e.g., daily or hourly) to keep events updated.  
✅ **Uses Google Apps Script**, so no extra software is needed.  

---

## 📌 How It Works  

### **Two Google Calendars**
- 🏢 **Employee Shifts Calendar** → Stores shift schedules of employees. Employee's e-mail should be included in the guests list.
- 📅 **Company Events Calendar** → Stores events where employees need to be assigned. The script will automatically add employee's email to the guest list of the event

### **Automated Matching**
- 🔄 The script scans both calendars and **identifies time overlaps** between shifts and events.  
- 👥 Employees with shifts **during an event's time slot** are **automatically added as guests**.  

### **Scheduled Execution**
- ⏳ Set up a **Google Apps Script trigger** to run the automation at regular intervals.  

---

## 🛠️ Installation & Setup  

### **1️⃣ Get Your Calendar IDs**  
1. Go to [Google Calendar](https://calendar.google.com/).  
2. Find the **Employee Shifts Calendar** and **Company Events Calendar**.  
3. Click **Settings & Sharing** → Scroll down to **Integrate Calendar** → Copy the **Calendar ID**.  

### **2️⃣ Set Up the Google Apps Script**  
1. Open [Google Apps Script](https://script.google.com/).  
2. Create a **new project** and paste the following script:  

```javascript
function assignEmployeesToEvents() {
    var shiftsCalendarId = 'YOUR_SHIFTS_CALENDAR_ID'; // Replace with Employee Shifts Calendar ID
    var eventsCalendarId = 'YOUR_EVENTS_CALENDAR_ID'; // Replace with Company Events Calendar ID

    var shiftsCalendar = CalendarApp.getCalendarById(shiftsCalendarId);
    var eventsCalendar = CalendarApp.getCalendarById(eventsCalendarId);

    var now = new Date();
    var future = new Date();
    future.setDate(now.getDate() + 7); // Adjust as needed

    var shifts = shiftsCalendar.getEvents(now, future);
    var events = eventsCalendar.getEvents(now, future);

    var shiftDetails = [];

    shifts.forEach(function(shift) {
        var shiftStart = shift.getStartTime();
        var shiftEnd = shift.getEndTime();
        var guests = shift.getGuestList();
        guests.forEach(function(guest) {
            shiftDetails.push({
                email: guest.getEmail(),
                start: shiftStart,
                end: shiftEnd
            });
        });
    });

    events.forEach(function(event) {
        var eventStart = event.getStartTime();
        var eventEnd = event.getEndTime();
        var addedGuests = [];

        shiftDetails.forEach(function(shift) {
            if (shift.end > eventStart && shift.start < eventEnd) {
                if (!addedGuests.includes(shift.email)) {
                    event.addGuest(shift.email);
                    addedGuests.push(shift.email);
                }
            }
        });
    });
}
```
3. **Replace** `YOUR_SHIFTS_CALENDAR_ID` **and** `YOUR_EVENTS_CALENDAR_ID` **with your actual calendar IDs.**  
4. Click **Save**.  

---

## ⏳ Set Up an Automatic Trigger  

1. Open **Triggers** in Google Apps Script (`🕒` clock icon).  
2. Click **+ Add Trigger**.  
3. Configure the trigger:  
   - **Function to run:** `assignEmployeesToEvents`  
   - **Event source:** `Time-driven`  
   - **Type:** `Day timer` (or adjust as needed)  
   - **Time of day:** Select your preferred execution time  
4. Click **Save**.  

---

## 📸 Screenshots  
*(Optional: Add screenshots of your Google Calendar setup or script execution.)*  

---

## 💡 Use Cases  
✔ **HR Scheduling** – Assign employees to relevant company events automatically.  
✔ **Event Management** – Keep guest lists updated for shift-based roles.  
✔ **Automated Scheduling** – Reduce manual errors and save time.  

---

## 🤝 Contributing  
🙌 Contributions are welcome! If you have improvements, feel free to submit a **pull request**.  

---

## 📜 License  
📝 This project is licensed under the **MIT License** – free to use and modify.  

---

## 🚀 Future Improvements  
🔹 Add Google Sheets integration for easier shift management.  
🔹 Implement Slack/Email notifications for employees.  
🔹 Build a user-friendly dashboard for shift monitoring.  

---

## 📬 Contact  
📧 If you have questions, feel free to open an **issue** or reach out at `your-email@example.com`.  

---

### **🚀 Enjoy hassle-free scheduling with Shift2Event!** 🎉
