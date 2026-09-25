# Project Testing Phase

## 1. Testing Objective
To verify that Scripted ACL correctly restricts access based on field value.

## 2. Test Cases

### Test Case 1: Critical Priority Record
- Login as user with itil role (no admin)
- Try to open incident with priority = 1 - Critical
- Expected: Access denied / Read-only
- Result: PASS

### Test Case 2: Admin Access
- Login as admin
- Open same Critical incident
- Expected: Full access allowed
- Result: PASS

### Test Case 3: Closed State
- State = Closed (7)
- Any non-admin user tries to edit
- Expected: Write operation denied
- Result: PASS

### Test Case 4: Normal Record
- Priority = 3 - Moderate, State = New
- Any itil user
- Expected: Access allowed
- Result: PASS

## 3. Testing Method
- Use Impersonate User feature in ServiceNow
- Check ACL logs: System Security -> Access Control -> Debug

## 4. Bug Fixes
- Initially admin also blocked -> Fixed by adding gs.hasRole('admin') check
- Answer variable not set -> Fixed by default answer = true

## 5. Conclusion
ACL works as expected for field-based restriction.
