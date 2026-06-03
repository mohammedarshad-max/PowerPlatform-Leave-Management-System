# Enterprise Leave Request & Approval Automation

## 📌 Business Problem
Manual leave requests get lost in email chains, lacking auditability and causing scheduling conflicts. Managers need a streamlined way to approve requests directly from their inbox without logging into a separate HR system.

## 💡 Solution Architecture
An end-to-end Power Platform solution that handles data entry, secure storage, and closed-loop manager approvals.
[Architecture Diagram](Architecture.png)

## 🖥️ User Interface (Power Apps)
The canvas app provides UI to input the leave request form details and submit the requests.
* **Dashboard:** Real-time tracking of historical requests.
* **Submission Form:** `Patch()` function writes directly to Dataverse.

**Homepage View:**
![Dashboard](home.png)
**Form View:**
![Form](inputform.png)

## ⚙️ Backend Automation (Power Automate & Dataverse)
The system uses Dataverse as a secure relational database. A Power Automate cloud flow listens for new rows, dispatching an Actionable Message to the manager's Outlook. 
After manager's input updates the row in dataverse and display in requests gallery.

**Flow Orchestration:**
![Flow Logic](Flow-routing-for-Approvals.png)
!Dataverse(Dataverse.png)

## 📥 Deployment
1. Download the unmanaged `.zip` solution from this repository.
2. Import into your Power Platform environment.
3. Establish connection references for Microsoft Dataverse and Approvals.
