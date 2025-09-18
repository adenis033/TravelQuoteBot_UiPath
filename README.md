# TravelQuoteBot – Automated Travel Cost Reply

This project automates the **“TravelQuoteBot”** process for handling travel requests in the **Customer Service / Sales Department of a Tourist Company**.  
Using **UiPath**, the robot collects customer requests, calculates estimated travel costs from predefined data, and automatically replies via email with a personalized trip summary.

---

## 📌 Project Overview
The automation manages incoming customer requests by:
- Reading trip request details from a **web form (Excel export)**.
- Validating customer data (destination, persons, days).
- Retrieving travel cost data (flights, daily budgets, accommodation, activities).
- Calculating total estimated trip costs.
- Composing and sending **personalized email replies** to customers.
- Logging and updating queue items with status (✅ Successful / ⚠️ Business Exception / ❌ System Exception).

---

## ✨ Features
- ⏱ **80% faster processing** compared to manual handling.  
- 🤖 **End-to-end automation** – from input to customer reply.  
- 🛡 **Robust exception handling** for missing data, email failures, or queue errors.  
- 📊 **Orchestrator-based monitoring & reporting**.  
- 🔄 **Scalable design** to handle seasonal peaks (up to 300% increase).  

---

## 🛠 Tech Stack
- **UiPath Studio 2025.x** – workflow design and automation.  
- **UiPath Orchestrator (Cloud)** – queue management, scheduling, and logs.  
- **Microsoft Excel 2016+** – cost database (read-only).  
- **Email Client (SMTP/Outlook)** – sending automated travel cost replies.  
- **Custom Web Form** – collects customer trip requests.  

---

## ⚙️ Process Flow
### AS-IS (Before Automation)
1. Customer submits travel request via web form.  
2. Staff manually checks Excel for destination costs.  
3. Staff prepares email with estimated price and breakdown.  
4. Staff replies to customer.  

### TO-BE (Automated)
1. Robot reads new trip requests from Excel.  
2. Validates input (destination, persons, days).  
3. Adds request to **Orchestrator Queue**.  
4. Retrieves cost data from Excel.  
5. Composes personalized email (summary + breakdown).  
6. Sends email to customer.  
7. Updates queue status and logs result.  

---

## 🚨 Exception Handling
- **Input Excel missing** → log + notify support.  
- **Invalid customer data** → skip row + log warning.  
- **Queue unavailable** → retry 3 times, stop if failing.  
- **Destination not found** → mark as Business Exception.  
- **Email sending failure** → retry 3 times, else System Exception.  
- **Unexpected errors** → log details, notify support.  

---

## 📊 Reporting
- **Daily logs** → number of processed requests, runtime.  
- **Transaction logs** → Successful / Business Exception / System Exception.  
- **Error logs** → timestamps, screenshots, and error categories.  
- **Email logs** → summary of all outgoing replies.  
- **Monthly performance summary** via UiPath Insights.  

---

## 🚀 Getting Started
1. Clone this repository:
   ```bash
   git clone https://github.com/adenis033/TravelQuoteBot_UiPath.git
2. Open the **Dispatcher.xaml** and **Performer.xaml** workflows in **UiPath Studio**.
3. Configure Orchestrator assets:
   * Queue: `TripQueue`
   * Credentials for email server
4. Run Dispatcher → upload requests to queue.
5. Run Performer → process queue items and send replies.

---

## 👨‍💻 Author

* **RÂPA Denis-Andrei**
  [GitHub Profile](https://github.com/adenis033)


