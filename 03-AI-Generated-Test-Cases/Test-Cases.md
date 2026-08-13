# GenAI QA Testing - AI-Generated Test Cases

## 1. Overview

This document contains detailed test cases created using Generative AI assistance and reviewed by a QA Engineer.

The test cases are derived from the test scenarios documented in `02-Test-Scenarios/Test-Scenarios.md`.

The objective is to demonstrate how Generative AI can accelerate test case creation while maintaining human validation, accuracy, traceability, and business relevance.

---

## 2. Test Case Format

| Field           | Description                          |
| --------------- | ------------------------------------ |
| Test Case ID    | Unique identifier                    |
| Scenario ID     | Related test scenario                |
| Module          | Application module                   |
| Test Case       | Detailed test objective              |
| Preconditions   | Conditions required before execution |
| Test Data       | Required input data                  |
| Steps           | Execution steps                      |
| Expected Result | Expected application behavior        |
| Priority        | Business/test priority               |
| Type            | Positive/Negative/Boundary/etc.      |
| AI Status       | AI Generated / QA Reviewed           |

---

# 3. User Registration Test Cases

## TC-GENAI-001

**Scenario ID:** TS-GENAI-001
**Module:** Registration
**Test Case:** Verify registration with valid user details
**Type:** Positive
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Preconditions

* Registration page is accessible.
* User does not already exist.

### Test Data

* Name: Test User
* Email: [testuser@example.com](mailto:testuser@example.com)
* Password: Test@12345

### Steps

1. Open the registration page.
2. Enter a valid name.
3. Enter a valid email address.
4. Enter a valid password.
5. Confirm the password.
6. Submit the registration form.

### Expected Result

The user should be successfully registered and redirected to the appropriate confirmation or application page.

---

## TC-GENAI-002

**Scenario ID:** TS-GENAI-002
**Module:** Registration
**Test Case:** Verify registration with mandatory fields empty
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Preconditions

* Registration page is accessible.

### Steps

1. Open the registration page.
2. Leave mandatory fields empty.
3. Click the Register button.

### Expected Result

Validation messages should be displayed for the required fields and registration should not proceed.

---

## TC-GENAI-003

**Scenario ID:** TS-GENAI-003
**Module:** Registration
**Test Case:** Verify registration with invalid email format
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Test Data

```text
invalid-email
user@
@example.com
user.com
```

### Steps

1. Open the registration page.
2. Enter valid values in other mandatory fields.
3. Enter an invalid email format.
4. Submit the form.

### Expected Result

The application should reject the invalid email and display an appropriate validation message.

---

## TC-GENAI-004

**Scenario ID:** TS-GENAI-004
**Module:** Registration
**Test Case:** Verify registration using an already registered email
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open the registration page.
2. Enter valid registration details.
3. Enter an email that already exists.
4. Submit the form.

### Expected Result

The application should prevent duplicate registration and display an appropriate message.

---

## TC-GENAI-005

**Scenario ID:** TS-GENAI-005
**Module:** Registration
**Test Case:** Verify password minimum length validation
**Type:** Boundary
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open registration.
2. Enter valid registration information.
3. Enter a password below the minimum allowed length.
4. Submit the form.

### Expected Result

The application should reject the password and display the applicable password requirement.

---

# 4. Login Test Cases

## TC-GENAI-006

**Scenario ID:** TS-GENAI-011
**Module:** Login
**Test Case:** Verify login with valid credentials
**Type:** Positive
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Test Data

```text
Email: testuser@example.com
Password: Test@12345
```

### Steps

1. Open the login page.
2. Enter a registered email.
3. Enter the correct password.
4. Click Login.

### Expected Result

The user should be successfully authenticated and redirected to the expected page.

---

## TC-GENAI-007

**Scenario ID:** TS-GENAI-012
**Module:** Login
**Test Case:** Verify login with invalid username
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open the login page.
2. Enter an unregistered email.
3. Enter a valid password.
4. Click Login.

### Expected Result

Login should fail and an appropriate authentication error should be displayed.

---

## TC-GENAI-008

**Scenario ID:** TS-GENAI-013
**Module:** Login
**Test Case:** Verify login with invalid password
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Enter a registered email.
2. Enter an incorrect password.
3. Click Login.

### Expected Result

Login should fail and the user should receive an appropriate error message.

---

## TC-GENAI-009

**Scenario ID:** TS-GENAI-014
**Module:** Login
**Test Case:** Verify login with blank username
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Leave username blank.
2. Enter a valid password.
3. Click Login.

### Expected Result

Username validation should be displayed and authentication should not occur.

---

## TC-GENAI-010

**Scenario ID:** TS-GENAI-018
**Module:** Login
**Test Case:** Verify forgot password functionality
**Type:** Functional
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open the Login page.
2. Click Forgot Password.
3. Enter a registered email.
4. Submit the request.

### Expected Result

The password recovery process should be initiated and the user should receive the appropriate recovery instructions.

---

# 5. Product Search Test Cases

## TC-GENAI-011

**Scenario ID:** TS-GENAI-021
**Module:** Product Search
**Test Case:** Verify search using a valid product name
**Type:** Positive
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Test Data

```text
Laptop
```

### Steps

1. Open the application.
2. Enter a valid product name in the search field.
3. Click Search.

### Expected Result

Relevant products matching the search term should be displayed.

---

## TC-GENAI-012

**Scenario ID:** TS-GENAI-022
**Module:** Product Search
**Test Case:** Verify search using partial product name
**Type:** Positive
**Priority:** Medium
**AI Status:** AI Generated + QA Reviewed

### Test Data

```text
lap
```

### Steps

1. Enter a partial product name.
2. Submit the search.

### Expected Result

Relevant matching products or search suggestions should be displayed.

---

## TC-GENAI-013

**Scenario ID:** TS-GENAI-023
**Module:** Product Search
**Test Case:** Verify search using invalid product name
**Type:** Negative
**Priority:** Medium
**AI Status:** AI Generated + QA Reviewed

### Test Data

```text
XYZUnknownProduct123
```

### Steps

1. Enter an unavailable product name.
2. Click Search.

### Expected Result

The application should display an appropriate no-results message.

---

## TC-GENAI-014

**Scenario ID:** TS-GENAI-024
**Module:** Product Search
**Test Case:** Verify search with empty input
**Type:** Negative
**Priority:** Medium
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Leave the search field empty.
2. Click Search.

### Expected Result

The application should either display a validation message or handle the request according to the defined requirement.

---

# 6. Product Details Test Cases

## TC-GENAI-015

**Scenario ID:** TS-GENAI-031
**Module:** Product Details
**Test Case:** Verify product details are displayed correctly
**Type:** Positive
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Search for a valid product.
2. Open the product details page.

### Expected Result

Product name, image, price, description, availability, and other applicable information should be displayed correctly.

---

## TC-GENAI-016

**Scenario ID:** TS-GENAI-033
**Module:** Product Details
**Test Case:** Verify product price
**Type:** Functional
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open a product details page.
2. Note the displayed price.
3. Compare it with the expected product price.

### Expected Result

The displayed price should match the configured product price.

---

# 7. Product Filter and Sorting Test Cases

## TC-GENAI-017

**Scenario ID:** TS-GENAI-039
**Module:** Product Filter
**Test Case:** Verify filtering products by category
**Type:** Functional
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open the product listing page.
2. Select a product category.
3. Apply the filter.

### Expected Result

Only products belonging to the selected category should be displayed.

---

## TC-GENAI-018

**Scenario ID:** TS-GENAI-040
**Module:** Product Filter
**Test Case:** Verify filtering products by price range
**Type:** Functional
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open the product listing page.
2. Select a valid minimum and maximum price.
3. Apply the filter.

### Expected Result

Products within the selected price range should be displayed.

---

# 8. Shopping Cart Test Cases

## TC-GENAI-019

**Scenario ID:** TS-GENAI-046
**Module:** Shopping Cart
**Test Case:** Verify adding a product to the cart
**Type:** Positive
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Search for a valid product.
2. Open the product details page.
3. Click Add to Cart.
4. Open the shopping cart.

### Expected Result

The selected product should appear in the cart with the correct quantity and price.

---

## TC-GENAI-020

**Scenario ID:** TS-GENAI-047
**Module:** Shopping Cart
**Test Case:** Verify removing a product from the cart
**Type:** Functional
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Add a product to the cart.
2. Open the cart.
3. Click Remove.

### Expected Result

The selected product should be removed and the cart total should be recalculated.

---

## TC-GENAI-021

**Scenario ID:** TS-GENAI-048
**Module:** Shopping Cart
**Test Case:** Verify updating product quantity
**Type:** Functional
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Add a product to the cart.
2. Change the quantity.
3. Save or apply the change.

### Expected Result

The product quantity and cart total should be updated correctly.

---

## TC-GENAI-022

**Scenario ID:** TS-GENAI-051
**Module:** Shopping Cart
**Test Case:** Verify cart total calculation
**Type:** Functional
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Add multiple products to the cart.
2. Note individual product prices and quantities.
3. Calculate the expected subtotal.
4. Compare it with the application total.

### Expected Result

The cart total should be calculated correctly based on product price and quantity.

---

# 9. Wishlist Test Cases

## TC-GENAI-023

**Scenario ID:** TS-GENAI-056
**Module:** Wishlist
**Test Case:** Verify adding a product to wishlist
**Type:** Positive
**Priority:** Medium
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open a product.
2. Click Add to Wishlist.
3. Open the wishlist.

### Expected Result

The selected product should appear in the wishlist.

---

## TC-GENAI-024

**Scenario ID:** TS-GENAI-057
**Module:** Wishlist
**Test Case:** Verify removing a product from wishlist
**Type:** Functional
**Priority:** Medium
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open the wishlist.
2. Select an existing product.
3. Remove it.

### Expected Result

The product should no longer appear in the wishlist.

---

# 10. Address Management Test Cases

## TC-GENAI-025

**Scenario ID:** TS-GENAI-061
**Module:** Address Management
**Test Case:** Verify adding a valid delivery address
**Type:** Positive
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Navigate to Address Management.
2. Click Add Address.
3. Enter valid address details.
4. Save the address.

### Expected Result

The address should be saved successfully and displayed in the user's address list.

---

## TC-GENAI-026

**Scenario ID:** TS-GENAI-063
**Module:** Address Management
**Test Case:** Verify invalid postal code validation
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open Add Address.
2. Enter valid address information.
3. Enter an invalid postal code.
4. Save the address.

### Expected Result

The application should reject the invalid postal code and display an appropriate validation message.

---

# 11. Checkout Test Cases

## TC-GENAI-027

**Scenario ID:** TS-GENAI-069
**Module:** Checkout
**Test Case:** Verify checkout with valid cart items
**Type:** Positive
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Preconditions

* User is logged in.
* Cart contains available products.
* Valid delivery address exists.

### Steps

1. Open the cart.
2. Click Checkout.
3. Select a delivery address.
4. Review the order summary.
5. Continue to payment.

### Expected Result

The user should proceed successfully to the payment stage.

---

## TC-GENAI-028

**Scenario ID:** TS-GENAI-070
**Module:** Checkout
**Test Case:** Verify checkout with empty cart
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Ensure the cart is empty.
2. Attempt to access checkout.

### Expected Result

The application should prevent checkout and display an appropriate message.

---

## TC-GENAI-029

**Scenario ID:** TS-GENAI-074
**Module:** Checkout
**Test Case:** Verify subtotal calculation
**Type:** Functional
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Add products with known prices and quantities.
2. Navigate to checkout.
3. Calculate the expected subtotal.
4. Compare it with the displayed subtotal.

### Expected Result

The subtotal should equal the sum of product price multiplied by quantity.

---

# 12. Payment Test Cases

## TC-GENAI-030

**Scenario ID:** TS-GENAI-078
**Module:** Payment
**Test Case:** Verify successful payment using valid payment details
**Type:** Positive
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Preconditions

* Valid order exists.
* Valid payment method is available.

### Steps

1. Proceed to payment.
2. Select a supported payment method.
3. Enter valid payment information.
4. Submit the payment.

### Expected Result

Payment should be processed successfully and the order should move to the appropriate confirmed status.

---

## TC-GENAI-031

**Scenario ID:** TS-GENAI-079
**Module:** Payment
**Test Case:** Verify payment failure handling
**Type:** Negative
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Proceed to payment.
2. Use a payment condition that results in failure.
3. Submit the payment.

### Expected Result

The application should display an appropriate payment failure message and should not incorrectly confirm the order.

---

## TC-GENAI-032

**Scenario ID:** TS-GENAI-083
**Module:** Payment
**Test Case:** Verify duplicate payment prevention
**Type:** Negative
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Initiate a payment.
2. Submit the payment.
3. Attempt to submit the same payment again rapidly.

### Expected Result

The application should prevent duplicate payment processing and should create only one valid transaction.

---

# 13. Order Management Test Cases

## TC-GENAI-033

**Scenario ID:** TS-GENAI-086
**Module:** Orders
**Test Case:** Verify successful order placement
**Type:** Positive
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Add a valid product to the cart.
2. Proceed through checkout.
3. Select a valid address.
4. Complete payment.

### Expected Result

The order should be successfully created and a unique order reference should be generated.

---

## TC-GENAI-034

**Scenario ID:** TS-GENAI-088
**Module:** Orders
**Test Case:** Verify order appears in order history
**Type:** Functional
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Place an order successfully.
2. Navigate to Order History.
3. Locate the latest order.

### Expected Result

The newly placed order should appear with correct order details and status.

---

## TC-GENAI-035

**Scenario ID:** TS-GENAI-090
**Module:** Orders
**Test Case:** Verify order cancellation
**Type:** Functional
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Open Order History.
2. Select an eligible order.
3. Click Cancel Order.
4. Confirm cancellation.

### Expected Result

The order should be cancelled successfully and its status should be updated accordingly.

---

# 14. Product Review Test Cases

## TC-GENAI-036

**Scenario ID:** TS-GENAI-094
**Module:** Product Reviews
**Test Case:** Verify submitting a valid product review
**Type:** Positive
**Priority:** Medium
**AI Status:** AI Generated + QA Reviewed

### Preconditions

* User has purchased or is eligible to review the product.

### Steps

1. Open the purchased product.
2. Select a valid rating.
3. Enter a valid review.
4. Submit the review.

### Expected Result

The review should be submitted successfully and displayed according to the application's review rules.

---

# 15. Logout Test Cases

## TC-GENAI-037

**Scenario ID:** TS-GENAI-099
**Module:** Authentication
**Test Case:** Verify successful logout
**Type:** Positive
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Login with valid credentials.
2. Open the user account menu.
3. Click Logout.

### Expected Result

The user should be logged out and redirected to the expected page.

---

## TC-GENAI-038

**Scenario ID:** TS-GENAI-100
**Module:** Authentication
**Test Case:** Verify protected pages cannot be accessed after logout
**Type:** Security
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Login successfully.
2. Navigate to a protected page.
3. Logout.
4. Attempt to access the protected page using the browser history or direct URL.

### Expected Result

The application should prevent unauthorized access and redirect the user to the login page or appropriate public page.

---

# 16. API Test Cases

## TC-GENAI-039

**Scenario ID:** TS-GENAI-103
**Module:** API
**Test Case:** Verify successful API response for valid request
**Type:** Positive
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Send a valid API request using Postman.
2. Capture the response.
3. Verify the HTTP status code.
4. Validate the response body.

### Expected Result

The API should return the expected successful status code and valid response data.

---

## TC-GENAI-040

**Scenario ID:** TS-GENAI-104
**Module:** API
**Test Case:** Verify API response status code
**Type:** Functional
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Send a valid API request.
2. Inspect the response status code.

### Expected Result

The response status code should match the expected status defined for the API operation.

---

## TC-GENAI-041

**Scenario ID:** TS-GENAI-106
**Module:** API
**Test Case:** Verify API behavior with missing mandatory parameter
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Prepare an API request.
2. Remove a mandatory parameter.
3. Send the request.

### Expected Result

The API should reject the request and return an appropriate error response.

---

## TC-GENAI-042

**Scenario ID:** TS-GENAI-108
**Module:** API
**Test Case:** Verify unauthorized API request
**Type:** Security
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Prepare an API request that requires authentication.
2. Remove or invalidate authentication credentials.
3. Send the request.

### Expected Result

The API should reject the unauthorized request with the appropriate authentication/authorization response.

---

# 17. Negative and Edge-Case Test Cases

## TC-GENAI-043

**Scenario ID:** TS-GENAI-123
**Module:** Application
**Test Case:** Verify behavior when network connection is interrupted
**Type:** Negative
**Priority:** High
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Start a critical transaction.
2. Interrupt the network connection.
3. Continue the transaction.

### Expected Result

The application should handle the network failure gracefully and display an appropriate message without corrupting transaction data.

---

## TC-GENAI-044

**Scenario ID:** TS-GENAI-124
**Module:** Checkout
**Test Case:** Verify session expiration during checkout
**Type:** Edge
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Login and add a product to the cart.
2. Navigate to checkout.
3. Allow the session to expire.
4. Attempt to continue checkout.

### Expected Result

The application should handle the expired session securely and should not allow unauthorized completion of the transaction.

---

## TC-GENAI-045

**Scenario ID:** TS-GENAI-125
**Module:** Checkout
**Test Case:** Verify product becomes unavailable during checkout
**Type:** Edge
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Add an available product to the cart.
2. Proceed to checkout.
3. Make the product unavailable in the test environment.
4. Attempt to place the order.

### Expected Result

The application should identify the availability change and prevent an invalid order from being placed.

---

## TC-GENAI-046

**Scenario ID:** TS-GENAI-127
**Module:** Orders
**Test Case:** Verify duplicate order prevention after repeated submission
**Type:** Negative
**Priority:** Critical
**AI Status:** AI Generated + QA Reviewed

### Steps

1. Complete all checkout details.
2. Submit the order.
3. Immediately attempt to submit the order again.

### Expected Result

Only one order should be created for the transaction.

---

# 18. AI-Assisted Test Case Review

AI-generated test cases are reviewed before finalization.

### Review Process

1. Compare the test case against the requirement.
2. Validate the scenario-to-test-case mapping.
3. Check test steps for completeness.
4. Validate expected results.
5. Remove duplicate cases.
6. Identify missing negative scenarios.
7. Add boundary conditions.
8. Validate business logic.
9. Assign priority.
10. Approve the final test case.

---

# 19. AI-Generated vs QA-Reviewed Test Cases

| Aspect                   | AI Output         | QA Review                         |
| ------------------------ | ----------------- | --------------------------------- |
| Test scenario generation | Generated quickly | Validated against requirements    |
| Positive cases           | Generated         | Reviewed                          |
| Negative cases           | Suggested         | Expanded where required           |
| Boundary cases           | Suggested         | Verified                          |
| Edge cases               | Suggested         | Validated for relevance           |
| Test data                | Generated         | Checked for validity              |
| Expected results         | Generated         | Corrected if required             |
| Priority                 | Suggested         | Assigned based on business impact |
| Final approval           | Not applicable    | QA Engineer                       |

---

# 20. Test Case Quality Criteria

A test case is considered ready for execution when:

* The objective is clear.
* The scenario is traceable.
* Preconditions are defined.
* Test data is available.
* Steps are executable.
* Expected results are measurable.
* Priority is assigned.
* The test case is relevant to the requirement.
* Duplicate coverage has been removed.
* AI-generated assumptions have been validated.

---

# 21. Traceability

The test cases maintain traceability to the scenarios documented in:

`02-Test-Scenarios/Test-Scenarios.md`

Example:

```text
Requirement
    ↓
Test Scenario
    ↓
AI-Generated Test Case
    ↓
QA Review
    ↓
Test Execution
    ↓
Defect
    ↓
Retest / Regression
```

---

# 22. Summary

A selected set of detailed execution-ready test cases has been created from the AI-assisted test scenarios.

The test cases demonstrate:

* AI-assisted test design
* Functional testing
* Positive testing
* Negative testing
* Boundary testing
* Edge-case testing
* Authentication testing
* E-Commerce workflow testing
* API testing
* Security-related validation
* Human review of AI-generated content

