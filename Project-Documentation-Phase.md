# Project Documentation Phase

## 1. Project Title
Script-Controlled ACL: Restrict Record Access Based on Field Value

## 2. Project Summary
This project implements a Scripted ACL in ServiceNow that restricts read/write access to records based on specific field values like priority and state.

## 3. Key Features Implemented
- Scripted ACL on incident table
- Field-based condition: priority = 1 (Critical) and state = Closed
- Role-based check using gs.hasRole('admin')
- Admin override enabled

## 4. Tools & Technologies
- ServiceNow PDI (Personal Developer Instance)
- ACL (Access Control List)
- JavaScript (Glide API)
- GitHub for Documentation

## 5. Final ACL Script
```javascript
if (current.priority == '1' && !gs.hasRole('admin')) {
    answer = false; // Deny
} else if (current.state == '7') {
    answer = false; // Closed - No edit
} else {
    answer = true; // Allow
}
