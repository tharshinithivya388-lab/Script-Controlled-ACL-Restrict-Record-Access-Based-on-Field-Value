# Brainstorming & Ideation - Script Controlled ACL

## 1. Problem Statement
Restrict record access based on field value dynamically. 
Ex: If status = Closed, only admin/manager can read/write.

## 2. Why Scripted ACL vs Normal ACL?
- Normal ACL: Role based only
- Scripted ACL: Field value + Role + User + Logic based control
- More flexible, more secure

## 3. Ideas
- Idea 1: Use current.field_name in ACL script
- Idea 2: Check gs.hasRole() and current.assigned_to
- Idea 3: Use answer = false to deny access
- Example Logic: 
  if(current.status == 'closed' && !gs.hasRole('admin')) {
    answer = false;
  } else {
    answer = true;
  }

## 4. Use Cases
- HR: Salary field only for HR admin
- ITSM: Closed incident no edit for caller
- Finance: Amount > 10000 needs manager role

## 5. Testing Plan
- Test with different users / roles
- Test with different field values
- Impersonate and verify

## 6. Security Considerations
- Avoid hardcoding sys_id
- Use gs.getUser() efficiently
