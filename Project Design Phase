# Requirement Analysis Phase

## 1. Requirement Overview
To restrict record access based on field value using Scripted ACL in ServiceNow.

## 2. Functional Requirements
- If field `priority = 1 - Critical`, only `itil_admin` role can edit.
- If `state = Closed`, no one can write except admin.
- Read access should be controlled based on `assigned_to` user.

## 3. Technical Requirements
- Create Scripted ACL on target table (e.g., incident, custom table)
- ACL Type: record / write / read
- Script logic using `current`, `gs.hasRole()`, `gs.getUserID()`

## 4. Sample ACL Script
```javascript
// Scripted ACL - Restrict based on field value
if (current.priority == '1' && !gs.hasRole('itil_admin')) {
    answer = false; // Deny access
} else {
    answer = true; // Allow access
}
