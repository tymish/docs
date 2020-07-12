# 1.2 (Vendor) View invoices
```
As a vendor,
I want to view all my past invoices.
```

## Pre-condition
* [0.0 Login](/0-0-login.md)

## Primary flow
```
Given
  the vendor is logged in [0.0 Login]

when 
  the vendor opens the application

then
  the system displays all invoices
    in reverse chronological order
```