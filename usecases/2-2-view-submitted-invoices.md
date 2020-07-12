# 2.2 (Studio Manager) View submitted invoices
```
As a studio manager,
I want to view submitted invoices.
```

## Pre-condition
* [0.0 Login](/0-0-login.md)

## Primary flow
```
Given
  the studio manager is logged in [0.0 Login]

when
  the studio manager loads the application

then 
  the system displays all submitted invoices
    that need to be paid
```