# Tymish

Track, approve and manage invoices.

## Definition of Terms

`Invoice` - a record of services and their duration for financial compensation

`Submitted invoice` - an invoice that has been submitted, and is awaiting payment confirmation

`Vendor` - Person or company that provides services to the studio. e.g. Dance Teacher, Photographer, etc.

`Studio manager` - a person able to manage vendors, and view submitted invoices, but cannot pay invoices.

`Owner` - a studio manager that is able to pay invoice.

## Usecases

### Technical
* [0.0 Login](/usecases/0-0-login.md)

### Vendors
* [1.0 Register](/usecases/1-0-register.md)
* [1.1 Submit invoice](/usecases/1-1-submit-invoice.md)
* [1.2 View invoices](/usecases/1-2-view-invoices.md)

### Studio
* [2.0 Add vendor](/usecases/2-0-add-vendor.md)
* [2.1 View vendors](/usecases/2-1-view-vendors.md)
* [2.2 View submitted invoices](/usecases/2-2-view-submitted-invoices.md)
* [3.0 Pay invoice](usecases/3-0-pay-invoice.md)
* [3.1 View paid invoices](usecases/3-1-view-paid-invoices.md)

## Api Endpoints
* `POST /login` - [0.0 Login]
* `GET /vendors` - [2.1 View vendors]
* `GET /vendors/{id}/invoices` - [1.2 View invoices]
* `POST /vendors` - [2.0 Add vendor]
* `POST /vendor/{id}/register` - [1.0 Register]
* `POST /vendors/{id}/invoices` - [1.1 Submit invoice]
* `GET /invoices?status=submitted` - [2.2 View submimtted invoices]
* `GET /invoices?status=paid` - [3.1 View paid invoices]
* `POST /invoices/{id}/pay` - [3.0 Pay invoice]
