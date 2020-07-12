# 3.0 (Owner) Pay invoice
```
As Owner,
I want to mark a submitted invoice as paid.
```

## Pre-condition
* [0.0 Login](/0-0-login.md)

## Primary flow
```
Given
  a submitted invoice
  and the owner is logged in [0.0 Login]

when
  the owner submits the payment information
    for the invoice

then
  the system marks the invoice as paid,
  saves the invoice,
  notifies the vendor,
  and notifies the owner
```