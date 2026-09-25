# Project Development Phase

## 1. Development Steps

### Step 1: Create Table / Use Incident
- Navigate to System Definition -> Tables

### Step 2: Create ACL
- Go to System Security -> Access Control (ACL)
- New -> Table: incident, Operation: read/write, Type: record

### Step 3: Enable Script
- Check "Scripted" checkbox
- Write script:

```javascript
// ACL Script: Restrict based on field value
(function executeRule(current, previous) {
    // If priority is 1 - Critical, only admin can edit
    if (current.priority == '1') {
        if (gs.hasRole('admin')) {
            answer = true;
        } else {
            answer = false;
        }
    } else if (current.state == '7') { // Closed state
        answer = false;
    } else {
        answer = true;
    }
})(current, previous);
