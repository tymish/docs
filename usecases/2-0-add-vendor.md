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

## Mock
<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2F8fijF1Lx3iYFdKeOoUqvjz%2FAdd-Vendor%3Fnode-id%3D0%253A1&chrome=DOCUMENTATION" allowfullscreen></iframe>