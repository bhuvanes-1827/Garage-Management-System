# Validation Rules - Garage Management Project

This file documents the **Validation Rules** created for the Garage Management Salesforce project.

---

## 📌 Appointment Object

### Rule Name: `Vehicle`

* **Error Condition Formula:**

  ```
  NOT(REGEX(Vehicle_number_plate__c , "[A-Z]{2}[0-9]{2}[A-Z]{2}[0-9]{4}"))
  ```
* **Error Message:**

  ```
  Please enter valid number
  ```
* **Error Location:** Field → `Vehicle number plate`

✅ This rule ensures that the **Vehicle Number Plate** follows the format `AA00AA0000` (two letters, two digits, two letters, four digits).

---

## 📌 Billing Details and Feedback Object

### Rule Name: `rating_should_be_less_than_5`

* **Error Condition Formula:**

  ```
  NOT(REGEX(Rating_for_service__c , "[1-5]{1}"))
  ```
* **Error Message:**

  ```
  rating should be from 1 to 5
  ```
* **Error Location:** Field → `Rating for Service`

✅ This rule ensures that the **Rating for Service** can only be a value between **1 and 5**.

---

## ✅ Example Formatting Guidelines

When documenting validation rules:

* Use **Rule Name** in `backticks`
* Provide the **formula** in a fenced code block ( \`\`\` )
* Write the **Error Message** in a fenced code block ( \`\`\` )
* Specify the **Error Location** clearly

This structure makes the validation rules easy to read and replicate.
