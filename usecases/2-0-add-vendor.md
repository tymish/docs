# 2.0 (Studio Manager) Add vendor
```
As a studio manager,
I want to add a new vendor.
```

## Pre-condition
* [0.0 Login](/0-0-login.md)

## Primary flow
```
Given
  the studio manager is logged in [0.0 Login]
  and has the email address of the new vendor

when
  the studio manager submits the new vendor email address

then
  the system sends a url to the new vendor
  and notifies the studio manager that the url is sent.
```