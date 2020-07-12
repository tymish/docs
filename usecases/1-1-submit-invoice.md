# 1.1 (Vendor) Submit invoice
```
As a vendor,
I want to submit my invoice.
```

## Pre-condition
* [0.0 Login](/0-0-login.md)

## Primary flow
```
Given
  the vendor is logged in [0.0 Login]

when
  the vendor creates a new invoice
  fills in the details,
  and submits

then
  the system saves the invoice,
  marks it as submitted,
  notifies the owner,
  and notifies the vendor
```
