# 1.2 Request time reports
```
As a studio manager,
I want to send out time reports for employees to submit.
```

## Use Cases

### Primary Flow
```
Given a list of employees,

when a user requests time reports from the system

time reports are created for each Employee
    for this month
and are emailed to each email address.

the system will show a list of employees
with time report statuses.
```

### Alternate Flow 1 - No employees
```
Given no employees in the system,

when a user requests time reports,

the system will notify the user that they need to fire add employees.
```

### Alternate Flow 2 - Reports already requested
```
Given a list of employees
but time reports have already been requested,

when a user requests time reports,

the system will notify the user that time reports have already been requested.
```

