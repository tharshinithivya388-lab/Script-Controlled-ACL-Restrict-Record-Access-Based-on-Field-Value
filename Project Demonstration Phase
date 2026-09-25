# Project Demonstration Phase

## 1. Demonstration Title
Script-Controlled ACL: Restrict Record Access Based on Field Value

## 2. Objective of Demo
To demonstrate how record access is restricted dynamically when field value changes.

## 3. Demo Flow

### Step 1: Create Test Record
- Table: incident
- Priority: 1 - Critical
- Assigned to: Test User

### Step 2: Impersonate as ITIL User
- Login as ITIL user (non-admin)
- Try to edit critical incident
- Output: Access Denied message

### Step 3: Impersonate as Admin
- Login as Admin
- Open same record
- Output: Access Allowed - can edit

### Step 4: Change Field Value
- Change priority from 1 to 3
- Again try as ITIL user
- Output: Now access allowed

### Step 5: Closed State Check
- State = Closed
- Try to edit as ITIL
- Output: Write operation not allowed

## 4. Video / Screenshot Evidence
- Screenshot 1: ACL Configuration
- Screenshot 2: Access Denied for ITIL
- Screenshot 3: Access Allowed for Admin
- Screenshot 4: Debug log

## 5. Key Points Explained in Demo
- How answer = true/false works in ACL script
- Difference between record ACL and field ACL
- Importance of Admin Override

## 6. Conclusion
Demo proves ACL restricts based on field value successfully, improving security.
