# Garage Management - Salesforce Project

This project implements a **Garage Management System** in Salesforce by creating custom objects and fields. Below is the step-by-step documentation of all fields created in the related objects.

---

## 📌 Customer Details Object

### Fields Created:

1. **Phone Field**

   * Field Label: `Phone number`
   * Data Type: `Phone`

2. **Email Field**

   * Field Label: `Gmail`
   * Data Type: `Email`

---

## 📌 Appointment Object

### Lookup Fields

* **Customer Lookup** → Lookup Relationship with `Customer Details`

### Checkbox Fields

1. **Maintenance service**
2. **Repairs**
3. \*\*Replacement Parts\`

(All checkboxes: Default Value = Unchecked)

### Date Field

* Field Label: `Appointment Date`
* Data Type: `Date`
* Required: ✅ Yes

### Currency Field

* Field Label: `Service Amount`
* Data Type: `Currency`
* Field-level security: Read-only for all profiles

### Text Field

* Field Label: `Vehicle number plate`
* Data Type: `Text`
* Length: `10`
* Required: ✅ Yes
* Unique: ✅ Yes

---

## 📌 Service Records Object

### Lookup Fields

* **Appointment Lookup** → Lookup Relationship with `Appointment`

  * Required: ✅ Yes
  * Lookup Filter: `Appointment: Appointment Date < Appointment: Created Date`
  * Error Message: `Value does not match the criteria`

### Checkbox Field

* Field Label: `Quality Check Status`
* Data Type: `Checkbox`
* Default Value: Unchecked

### Picklist Field

* Field Label: `Service Status`
* Values: `Started, Completed`

### Formula Field

* Field Label: `Service Date`
* Data Type: `Formula (Date)`
* Formula: `CreatedDate`

---

## 📌 Billing Details and Feedback Object

### Lookup Fields

* **Service Records Lookup** → Lookup Relationship with `Service Records`

### Currency Field

* Field Label: `Payment Paid`
* Data Type: `Currency`

### Text Field

* Field Label: `Rating for service`
* Data Type: `Text`
* Length: `1`
* Required: ✅ Yes

### Picklist Field

* Field Label: `Payment Status`
* Values: `Pending, Completed`

---

## ✅ Summary

This Garage Management system in Salesforce is designed with the following key features:

* **Customer Details** object to store customer phone and Gmail.
* **Appointments** to track services, costs, and vehicles.
* **Service Records** to manage services, quality checks, and statuses.
* **Billing & Feedback** to handle payments and service ratings.

All fields have been carefully configured with lookup relationships, validation rules, filters, and security settings to ensure smooth management of garage operations.
