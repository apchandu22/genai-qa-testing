# GenAI QA Testing - Test Scenarios

## 1. Overview

This document contains functional and non-functional test scenarios generated using a combination of traditional QA techniques and Generative AI assistance.

The scenarios are based on an E-Commerce application and cover major user workflows including registration, login, product search, product details, cart, checkout, payment, orders, and API validation.

All AI-generated scenarios are reviewed and refined by the QA Engineer before being considered final test scenarios.

---

## 2. Scenario Identification

### Scenario ID Format

`TS-GENAI-XXX`

Example:

`TS-GENAI-001`

---

## 3. User Registration

| Scenario ID  | Test Scenario                                            | Type     | Priority |
| ------------ | -------------------------------------------------------- | -------- | -------- |
| TS-GENAI-001 | Verify registration with valid user details              | Positive | High     |
| TS-GENAI-002 | Verify registration with mandatory fields empty          | Negative | High     |
| TS-GENAI-003 | Verify registration with invalid email format            | Negative | High     |
| TS-GENAI-004 | Verify registration with an already registered email     | Negative | High     |
| TS-GENAI-005 | Verify password minimum length validation                | Boundary | High     |
| TS-GENAI-006 | Verify password maximum length validation                | Boundary | Medium   |
| TS-GENAI-007 | Verify password and confirm password mismatch            | Negative | High     |
| TS-GENAI-008 | Verify registration with special characters              | Negative | Medium   |
| TS-GENAI-009 | Verify email field accepts valid email formats           | Positive | Medium   |
| TS-GENAI-010 | Verify validation messages for invalid registration data | Negative | Medium   |

---

## 4. Login

| Scenario ID  | Test Scenario                                          | Type       | Priority |
| ------------ | ------------------------------------------------------ | ---------- | -------- |
| TS-GENAI-011 | Verify login with valid credentials                    | Positive   | Critical |
| TS-GENAI-012 | Verify login with invalid username                     | Negative   | High     |
| TS-GENAI-013 | Verify login with invalid password                     | Negative   | High     |
| TS-GENAI-014 | Verify login with blank username                       | Negative   | High     |
| TS-GENAI-015 | Verify login with blank password                       | Negative   | High     |
| TS-GENAI-016 | Verify login with both fields blank                    | Negative   | High     |
| TS-GENAI-017 | Verify password visibility functionality               | Functional | Medium   |
| TS-GENAI-018 | Verify forgot password functionality                   | Functional | High     |
| TS-GENAI-019 | Verify account behavior after multiple failed attempts | Security   | High     |
| TS-GENAI-020 | Verify successful login redirects to the expected page | Functional | High     |

---

## 5. Product Search

| Scenario ID  | Test Scenario                                         | Type       | Priority |
| ------------ | ----------------------------------------------------- | ---------- | -------- |
| TS-GENAI-021 | Verify search using a valid product name              | Positive   | High     |
| TS-GENAI-022 | Verify search using partial product name              | Positive   | Medium   |
| TS-GENAI-023 | Verify search using invalid product name              | Negative   | Medium   |
| TS-GENAI-024 | Verify search with empty input                        | Negative   | Medium   |
| TS-GENAI-025 | Verify search using special characters                | Negative   | Medium   |
| TS-GENAI-026 | Verify search using numeric input                     | Boundary   | Low      |
| TS-GENAI-027 | Verify search with leading and trailing spaces        | Edge       | Medium   |
| TS-GENAI-028 | Verify search with different letter casing            | Edge       | Low      |
| TS-GENAI-029 | Verify search results relevance                       | Functional | High     |
| TS-GENAI-030 | Verify search response when no products are available | Negative   | Medium   |

---

## 6. Product Details

| Scenario ID  | Test Scenario                                  | Type       | Priority |
| ------------ | ---------------------------------------------- | ---------- | -------- |
| TS-GENAI-031 | Verify product details are displayed correctly | Positive   | High     |
| TS-GENAI-032 | Verify product name is displayed correctly     | Functional | Medium   |
| TS-GENAI-033 | Verify product price is displayed correctly    | Functional | High     |
| TS-GENAI-034 | Verify product images are displayed correctly  | UI         | Medium   |
| TS-GENAI-035 | Verify product availability status             | Functional | High     |
| TS-GENAI-036 | Verify product description                     | Functional | Medium   |
| TS-GENAI-037 | Verify product quantity selection              | Functional | High     |
| TS-GENAI-038 | Verify unavailable product cannot be purchased | Negative   | High     |

---

## 7. Product Filtering and Sorting

| Scenario ID  | Test Scenario                                | Type       | Priority |
| ------------ | -------------------------------------------- | ---------- | -------- |
| TS-GENAI-039 | Verify filtering products by category        | Functional | High     |
| TS-GENAI-040 | Verify filtering products by price range     | Functional | High     |
| TS-GENAI-041 | Verify filtering using multiple filters      | Functional | High     |
| TS-GENAI-042 | Verify clearing applied filters              | Functional | Medium   |
| TS-GENAI-043 | Verify sorting products by price low to high | Functional | Medium   |
| TS-GENAI-044 | Verify sorting products by price high to low | Functional | Medium   |
| TS-GENAI-045 | Verify sorting products by relevance         | Functional | Medium   |

---

## 8. Shopping Cart

| Scenario ID  | Test Scenario                                       | Type       | Priority |
| ------------ | --------------------------------------------------- | ---------- | -------- |
| TS-GENAI-046 | Verify adding a product to the cart                 | Positive   | Critical |
| TS-GENAI-047 | Verify removing a product from the cart             | Functional | High     |
| TS-GENAI-048 | Verify updating product quantity                    | Functional | High     |
| TS-GENAI-049 | Verify minimum allowed quantity                     | Boundary   | High     |
| TS-GENAI-050 | Verify maximum allowed quantity                     | Boundary   | High     |
| TS-GENAI-051 | Verify cart total calculation                       | Functional | Critical |
| TS-GENAI-052 | Verify product price is reflected correctly in cart | Functional | High     |
| TS-GENAI-053 | Verify cart contents after page refresh             | Edge       | Medium   |
| TS-GENAI-054 | Verify cart contents after logout and login         | Edge       | Medium   |
| TS-GENAI-055 | Verify empty cart behavior                          | Negative   | Medium   |

---

## 9. Wishlist

| Scenario ID  | Test Scenario                                          | Type       | Priority |
| ------------ | ------------------------------------------------------ | ---------- | -------- |
| TS-GENAI-056 | Verify adding a product to wishlist                    | Positive   | Medium   |
| TS-GENAI-057 | Verify removing a product from wishlist                | Functional | Medium   |
| TS-GENAI-058 | Verify duplicate product cannot be added unnecessarily | Negative   | Low      |
| TS-GENAI-059 | Verify wishlist persistence after login                | Functional | Medium   |
| TS-GENAI-060 | Verify wishlist behavior for unavailable products      | Edge       | Low      |

---

## 10. Address Management

| Scenario ID  | Test Scenario                          | Type       | Priority |
| ------------ | -------------------------------------- | ---------- | -------- |
| TS-GENAI-061 | Verify adding a valid delivery address | Positive   | High     |
| TS-GENAI-062 | Verify mandatory address fields        | Negative   | High     |
| TS-GENAI-063 | Verify invalid postal code             | Negative   | High     |
| TS-GENAI-064 | Verify invalid phone number            | Negative   | Medium   |
| TS-GENAI-065 | Verify maximum address field length    | Boundary   | Medium   |
| TS-GENAI-066 | Verify editing an existing address     | Functional | Medium   |
| TS-GENAI-067 | Verify deleting an existing address    | Functional | Medium   |
| TS-GENAI-068 | Verify selecting a default address     | Functional | High     |

---

## 11. Checkout

| Scenario ID  | Test Scenario                              | Type       | Priority |
| ------------ | ------------------------------------------ | ---------- | -------- |
| TS-GENAI-069 | Verify checkout with valid cart items      | Positive   | Critical |
| TS-GENAI-070 | Verify checkout with an empty cart         | Negative   | High     |
| TS-GENAI-071 | Verify delivery address selection          | Functional | High     |
| TS-GENAI-072 | Verify order summary before payment        | Functional | Critical |
| TS-GENAI-073 | Verify product quantities in order summary | Functional | High     |
| TS-GENAI-074 | Verify subtotal calculation                | Functional | Critical |
| TS-GENAI-075 | Verify tax calculation                     | Functional | High     |
| TS-GENAI-076 | Verify delivery charges                    | Functional | Medium   |
| TS-GENAI-077 | Verify final order total                   | Functional | Critical |

---

## 12. Payment

| Scenario ID  | Test Scenario                                         | Type       | Priority |
| ------------ | ----------------------------------------------------- | ---------- | -------- |
| TS-GENAI-078 | Verify successful payment using valid payment details | Positive   | Critical |
| TS-GENAI-079 | Verify payment failure handling                       | Negative   | Critical |
| TS-GENAI-080 | Verify invalid payment information                    | Negative   | High     |
| TS-GENAI-081 | Verify payment cancellation                           | Negative   | High     |
| TS-GENAI-082 | Verify payment timeout handling                       | Edge       | High     |
| TS-GENAI-083 | Verify duplicate payment prevention                   | Negative   | Critical |
| TS-GENAI-084 | Verify order status after successful payment          | Functional | Critical |
| TS-GENAI-085 | Verify order status after failed payment              | Functional | High     |

---

## 13. Order Management

| Scenario ID  | Test Scenario                                  | Type       | Priority |
| ------------ | ---------------------------------------------- | ---------- | -------- |
| TS-GENAI-086 | Verify successful order placement              | Positive   | Critical |
| TS-GENAI-087 | Verify order confirmation                      | Functional | Critical |
| TS-GENAI-088 | Verify order appears in order history          | Functional | High     |
| TS-GENAI-089 | Verify order details                           | Functional | High     |
| TS-GENAI-090 | Verify order cancellation                      | Functional | High     |
| TS-GENAI-091 | Verify cancellation after order status changes | Negative   | High     |
| TS-GENAI-092 | Verify order status updates                    | Functional | High     |
| TS-GENAI-093 | Verify order history for users with no orders  | Negative   | Medium   |

---

## 14. Product Reviews

| Scenario ID  | Test Scenario                            | Type       | Priority |
| ------------ | ---------------------------------------- | ---------- | -------- |
| TS-GENAI-094 | Verify submitting a valid product review | Positive   | Medium   |
| TS-GENAI-095 | Verify submitting an empty review        | Negative   | Low      |
| TS-GENAI-096 | Verify review character limit            | Boundary   | Low      |
| TS-GENAI-097 | Verify rating selection                  | Functional | Medium   |
| TS-GENAI-098 | Verify duplicate review restrictions     | Negative   | Medium   |

---

## 15. Logout

| Scenario ID  | Test Scenario                                          | Type     | Priority |
| ------------ | ------------------------------------------------------ | -------- | -------- |
| TS-GENAI-099 | Verify successful logout                               | Positive | High     |
| TS-GENAI-100 | Verify protected pages cannot be accessed after logout | Security | High     |
| TS-GENAI-101 | Verify browser back button behavior after logout       | Security | High     |
| TS-GENAI-102 | Verify session termination after logout                | Security | High     |

---

## 16. API Testing Scenarios

| Scenario ID  | Test Scenario                                            | Type       | Priority |
| ------------ | -------------------------------------------------------- | ---------- | -------- |
| TS-GENAI-103 | Verify API returns successful response for valid request | Positive   | Critical |
| TS-GENAI-104 | Verify API response status code                          | Functional | High     |
| TS-GENAI-105 | Verify response body schema                              | Functional | High     |
| TS-GENAI-106 | Verify API behavior with missing mandatory parameters    | Negative   | High     |
| TS-GENAI-107 | Verify API behavior with invalid parameters              | Negative   | High     |
| TS-GENAI-108 | Verify unauthorized API request                          | Security   | High     |
| TS-GENAI-109 | Verify invalid authentication token                      | Security   | High     |
| TS-GENAI-110 | Verify API response for nonexistent resource             | Negative   | Medium   |
| TS-GENAI-111 | Verify API response headers                              | Functional | Medium   |
| TS-GENAI-112 | Verify API response data consistency                     | Functional | High     |

---

## 17. Cross-Browser Scenarios

| Scenario ID  | Test Scenario                                       | Type          | Priority |
| ------------ | --------------------------------------------------- | ------------- | -------- |
| TS-GENAI-113 | Verify login across supported browsers              | Compatibility | High     |
| TS-GENAI-114 | Verify product search across supported browsers     | Compatibility | Medium   |
| TS-GENAI-115 | Verify cart functionality across supported browsers | Compatibility | High     |
| TS-GENAI-116 | Verify checkout across supported browsers           | Compatibility | Critical |
| TS-GENAI-117 | Verify UI layout across supported browsers          | UI            | Medium   |

---

## 18. Responsive and Mobile Scenarios

| Scenario ID  | Test Scenario                                            | Type       | Priority |
| ------------ | -------------------------------------------------------- | ---------- | -------- |
| TS-GENAI-118 | Verify application responsiveness on mobile screen sizes | UI         | High     |
| TS-GENAI-119 | Verify navigation on mobile devices                      | Functional | High     |
| TS-GENAI-120 | Verify product search on mobile                          | Functional | Medium   |
| TS-GENAI-121 | Verify cart functionality on mobile                      | Functional | High     |
| TS-GENAI-122 | Verify checkout workflow on mobile                       | Functional | Critical |

---

## 19. Negative and Edge-Case Scenarios

| Scenario ID  | Test Scenario                                                    | Type     | Priority |
| ------------ | ---------------------------------------------------------------- | -------- | -------- |
| TS-GENAI-123 | Verify behavior when network connection is interrupted           | Negative | High     |
| TS-GENAI-124 | Verify behavior when session expires during checkout             | Edge     | Critical |
| TS-GENAI-125 | Verify behavior when product becomes unavailable during checkout | Edge     | Critical |
| TS-GENAI-126 | Verify behavior when payment response is delayed                 | Edge     | High     |
| TS-GENAI-127 | Verify duplicate order prevention after repeated submission      | Negative | Critical |
| TS-GENAI-128 | Verify application behavior after page refresh during checkout   | Edge     | High     |
| TS-GENAI-129 | Verify handling of unexpected server errors                      | Negative | High     |
| TS-GENAI-130 | Verify graceful error messages for failed operations             | Negative | Medium   |

---

## 20. AI-Assisted Scenario Generation

Generative AI was used to identify additional scenarios that may be missed during traditional test design.

The AI-assisted approach focuses on:

* Positive scenarios
* Negative scenarios
* Boundary conditions
* Edge cases
* Alternate workflows
* Error conditions
* Validation rules
* Integration points
* Session-related conditions
* Payment-related failures
* API failures

---

## 21. Human Review of AI-Generated Scenarios

AI-generated scenarios are reviewed using the following criteria:

| Review Criteria       | Validation                                                  |
| --------------------- | ----------------------------------------------------------- |
| Requirement relevance | Scenario must map to application functionality              |
| Business relevance    | Scenario must represent a realistic user/business condition |
| Testability           | Scenario must be possible to execute                        |
| Duplicate detection   | Duplicate scenarios are removed                             |
| Coverage              | Missing conditions are added                                |
| Accuracy              | Incorrect AI assumptions are removed                        |
| Priority              | Business-critical scenarios receive higher priority         |

---

## 22. Scenario Prioritization

Scenarios are prioritized based on:

* Business impact
* User impact
* Risk
* Frequency of use
* Integration complexity
* Defect history
* Critical business workflows

Critical workflows such as login, cart, checkout, payment, and order placement receive higher testing priority.

---

## 23. Expected Outcome

The final scenario set should provide broad coverage of the E-Commerce application while demonstrating how GenAI can assist QA Engineers in identifying additional testing conditions.

The QA Engineer remains responsible for validating all AI-generated scenarios and ensuring that the final scenarios accurately represent application requirements.

---

## 24. Summary

A total of **130 test scenarios** have been identified across major application areas.

The scenarios include:

* Functional testing
* Positive testing
* Negative testing
* Boundary testing
* Edge-case testing
* API testing
* Compatibility testing
* Responsive testing
* Security-related validation
* AI-assisted scenario generation


