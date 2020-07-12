# 1.1 (Vendor) Register
```
As a vendor,
I want to complete my registration for an account.
```

### Pre-condition
* [2.0 Add vendor](/2-0-add-vendor.md)

### Primary Flow
```
Given
  a url to register an account
    that was triggered from [2.0 Add vendor]

when
  the vendor navigates to the url in a browser
  the system loads a registration form.

then, when
  the vendor submits the form,
  the system completes their registration
    and notifies the vedor.
```
