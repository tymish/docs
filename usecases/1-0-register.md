# 1.0 (Vendor) Register
```
As a vendor,
I want to complete my registration for an account.
```

## Pre-condition
* [2.0 Add vendor](/2-0-add-vendor.md)

## Primary flow
```
Given
  a url to register an account
    that was triggered from [2.0 Add vendor]

when
  the vendor navigates to the url in a browser
  
then
  the system loads a registration form

when
  the vendor fills
  and submits the form

then
  the system completes their registration
  and notifies the vendor.
```

## Mock
<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FqNVLyEThgTXwIqeIVHajKh%2FVendor-Register%3Fnode-id%3D0%253A1&chrome=DOCUMENTATION" allowfullscreen></iframe>