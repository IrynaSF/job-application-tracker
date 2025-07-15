# 🧠 Project Notes – Job Application Tracker

## 📍 Goal

Create a job application tracker on the Salesforce platform to practice custom object creation, validation rules, formula fields, and UI customization as part of my learning path toward becoming a Salesforce Developer.

---

## 🧱 Steps Taken

1. **Created Custom Object:**  
   - Name: `Job Application`  
   - Enabled Allow Reports and Track Activities

2. **Added Custom Fields:**  
   - `Company` (Text)  
   - `Position` (Text)  
   - `Application Date` (Date)  
   - `Interview Date` (Date)  
   - `Status` (Picklist) — values: Applied, Interview Scheduled, Offer, Rejected

3. **Created Validation Rule:**  
   - Rule Name: `Future_Application_Date`  
   - Purpose: Prevent users from entering a future date in `Application Date`  
   - Formula used:  
     ```text
     Application_Date__c > TODAY()
     ```  
   - Error message: *"Please enter a date that is today or earlier."*

4. **Created Formula Field:**  
   - Field Name: `Application Days Count`  
   - Type: Number  
   - Formula used:  
     ```text
     ABS(TODAY() - Application_Date__c)
     ```  
   - Purpose: Shows how many days have passed since the application was submitted.

5. **UI Customization:**  
   - Adjusted Page Layout to display custom fields clearly  
   - Set field order and section labels

---

## 🧪 What I Learned

- How to create and configure a **custom object** in Salesforce
- Writing **validation rules** using logical expressions and functions
- Using **formula fields** to calculate dynamic values like date differences
- Working with Salesforce's **App Builder UI** to control layout and visibility
- The importance of user-friendly error messages

---

## 🔄 Challenges and Fixes

- At first, I used `Application_Date__c - TODAY()` which gave negative values. Fixed it using `ABS()` to always return a positive day count.
- I didn’t know where to insert formulas — learned to use **Advanced Formula** tab and “Insert Field” to avoid typos.
- Forgot to assign Page Layout to Profile — fixed it to make the custom object visible in the app.

---

## 📌 Next Steps

- Add automation: a Flow to update status based on interview date
- Practice with related records: link Applications to Contacts or Accounts
- Deploy the app to a Trailhead Playground or Developer Org and share as a demo
