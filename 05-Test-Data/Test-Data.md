# GenAI QA Testing - Test Data

## 1. Overview

This document contains sample test data required for testing the E-Commerce application.

The data is designed to support:

* Positive testing
* Negative testing
* Boundary testing
* Validation testing
* API testing
* Checkout testing
* Payment testing
* Defect reproduction
* Edge-case testing

All data in this document is synthetic and must not represent real customer information.

---

## 2. Test Data Principles

The test data should:

* Be realistic enough for functional testing.
* Cover valid and invalid conditions.
* Include boundary values.
* Include negative scenarios.
* Avoid real personal information.
* Support repeatable test execution.
* Be reusable across test cases.
* Support API and UI testing.

---

# 3. User Registration Data

| Data ID    | Name            | Email                                                       | Password   | Type             |
| ---------- | --------------- | ----------------------------------------------------------- | ---------- | ---------------- |
| TD-REG-001 | Test User       | [testuser01@example.com](mailto:testuser01@example.com)     | Test@12345 | Valid            |
| TD-REG-002 | QA User         | [qauser01@example.com](mailto:qauser01@example.com)         | QaTest@123 | Valid            |
| TD-REG-003 | Automation User | [automation01@example.com](mailto:automation01@example.com) | Auto@12345 | Valid            |
| TD-REG-004 | Test User       | invalid-email                                               | Test@12345 | Invalid          |
| TD-REG-005 | Test User       | user@                                                       | Test@12345 | Invalid          |
| TD-REG-006 | Test User       | @example.com                                                | Test@12345 | Invalid          |
| TD-REG-007 | Test User       |                                                             | Test@12345 | Blank            |
| TD-REG-008 |                 | [testuser02@example.com](mailto:testuser02@example.com)     | Test@12345 | Blank Name       |
| TD-REG-009 | Test User       | [duplicate@example.com](mailto:duplicate@example.com)       | Test@12345 | Duplicate        |
| TD-REG-010 | Test User       | [testuser03@example.com](mailto:testuser03@example.com)     | 123        | Boundary/Invalid |

---

# 4. Login Data

| Data ID      | Username                                                | Password   | Type             |
| ------------ | ------------------------------------------------------- | ---------- | ---------------- |
| TD-LOGIN-001 | [testuser01@example.com](mailto:testuser01@example.com) | Test@12345 | Valid            |
| TD-LOGIN-002 | [testuser01@example.com](mailto:testuser01@example.com) | Wrong@123  | Invalid Password |
| TD-LOGIN-003 | [unknown@example.com](mailto:unknown@example.com)       | Test@12345 | Invalid User     |
| TD-LOGIN-004 |                                                         | Test@12345 | Blank Username   |
| TD-LOGIN-005 | [testuser01@example.com](mailto:testuser01@example.com) |            | Blank Password   |
| TD-LOGIN-006 |                                                         |            | Both Blank       |
| TD-LOGIN-007 | [TESTUSER01@EXAMPLE.COM](mailto:TESTUSER01@EXAMPLE.COM) | Test@12345 | Case Variation   |

---

# 5. Password Boundary Data

| Data ID    | Password                                 | Condition                  |
| ---------- | ---------------------------------------- | -------------------------- |
| TD-PWD-001 | 1234567                                  | Below minimum              |
| TD-PWD-002 | 12345678                                 | Minimum boundary           |
| TD-PWD-003 | 123456789                                | Minimum + 1                |
| TD-PWD-004 | Test@12345                               | Valid                      |
| TD-PWD-005 | Test@123456789                           | Valid                      |
| TD-PWD-006 | VeryLongPasswordValueForTesting123456789 | Maximum boundary candidate |
| TD-PWD-007 | 123456789012345678901234567890123456789  | Above maximum candidate    |

> Exact minimum and maximum limits must be replaced with the application's actual requirements when available.

---

# 6. Product Search Data

| Data ID       | Search Input         | Type                    |
| ------------- | -------------------- | ----------------------- |
| TD-SEARCH-001 | Laptop               | Valid                   |
| TD-SEARCH-002 | Mobile Phone         | Valid                   |
| TD-SEARCH-003 | Headphones           | Valid                   |
| TD-SEARCH-004 | lap                  | Partial                 |
| TD-SEARCH-005 | XYZUnknownProduct123 | No Result               |
| TD-SEARCH-006 |                      | Blank                   |
| TD-SEARCH-007 | @#$%                 | Special Characters      |
| TD-SEARCH-008 | 12345                | Numeric                 |
| TD-SEARCH-009 | Laptop               | Leading/Trailing Spaces |
| TD-SEARCH-010 | LAPTOP               | Case Variation          |

---

# 7. Product Quantity Data

| Data ID    | Quantity | Type                    |
| ---------- | -------: | ----------------------- |
| TD-QTY-001 |        0 | Below minimum           |
| TD-QTY-002 |        1 | Minimum candidate       |
| TD-QTY-003 |        2 | Valid                   |
| TD-QTY-004 |       10 | Valid                   |
| TD-QTY-005 |       99 | Maximum candidate       |
| TD-QTY-006 |      100 | Above maximum candidate |
| TD-QTY-007 |       -1 | Invalid                 |
| TD-QTY-008 |      ABC | Invalid                 |
| TD-QTY-009 |      1.5 | Decimal                 |

> Actual quantity limits should be validated against the application's requirements.

---

# 8. Address Test Data

| Data ID     | Name      | Address         | City      | State      | Postal Code | Phone      | Type           |
| ----------- | --------- | --------------- | --------- | ---------- | ----------- | ---------- | -------------- |
| TD-ADDR-001 | Test User | 123 Test Street | Bengaluru | Karnataka  | 560001      | 9000000001 | Valid          |
| TD-ADDR-002 | QA User   | 456 QA Road     | Hyderabad | Telangana  | 500001      | 9000000002 | Valid          |
| TD-ADDR-003 | Test User | 789 Demo Avenue | Chennai   | Tamil Nadu | 600001      | 9000000003 | Valid          |
| TD-ADDR-004 | Test User | 123 Test Street | Bengaluru | Karnataka  | ABC123      | 9000000004 | Invalid Postal |
| TD-ADDR-005 | Test User | 123 Test Street | Bengaluru | Karnataka  | 560001      | 123        | Invalid Phone  |
| TD-ADDR-006 |           | 123 Test Street | Bengaluru | Karnataka  | 560001      | 9000000005 | Blank Name     |
| TD-ADDR-007 | Test User |                 | Bengaluru | Karnataka  | 560001      | 9000000006 | Blank Address  |

---

# 9. Checkout Data

| Data ID      | Product             | Quantity | Address | Payment Type | Expected      |
| ------------ | ------------------- | -------: | ------- | ------------ | ------------- |
| TD-CHECK-001 | Laptop              |        1 | Valid   | Test Card    | Success       |
| TD-CHECK-002 | Mobile Phone        |        2 | Valid   | Test Card    | Success       |
| TD-CHECK-003 | Headphones          |        1 | Valid   | Test Payment | Success       |
| TD-CHECK-004 | Laptop              |        0 | Valid   | Test Card    | Validation    |
| TD-CHECK-005 | Laptop              |        1 | Invalid | Test Card    | Address Error |
| TD-CHECK-006 | Unavailable Product |        1 | Valid   | Test Card    | Product Error |

---

# 10. Payment Test Data

Only test/sandbox payment data should be used.

| Data ID    | Payment Condition           | Expected Result      |
| ---------- | --------------------------- | -------------------- |
| TD-PAY-001 | Valid sandbox payment       | Successful           |
| TD-PAY-002 | Declined sandbox payment    | Failed               |
| TD-PAY-003 | Invalid payment details     | Validation/Error     |
| TD-PAY-004 | Expired test payment method | Failure              |
| TD-PAY-005 | Cancelled payment           | Cancelled            |
| TD-PAY-006 | Payment timeout simulation  | Timeout Handling     |
| TD-PAY-007 | Duplicate submission        | Duplicate Prevention |

> Real card numbers, banking information, OTPs, or customer payment details must never be stored in this repository.

---

# 11. API Test Data

## 11.1 Valid Request

```json id="8e8t7q"
{
  "username": "testuser01",
  "email": "testuser01@example.com",
  "productId": "P1001",
  "quantity": 1
}
```

Expected:

```text id="qf6tyh"
HTTP 200 / 201
Valid response body
Expected response fields
```

---

## 11.2 Missing Parameter

```json id="m5jtp3"
{
  "username": "testuser01",
  "email": "testuser01@example.com"
}
```

Expected:

```text id="o1h1sf"
Request should be rejected if productId and quantity are mandatory.
```

---

## 11.3 Invalid Quantity

```json id="x8tkp0"
{
  "username": "testuser01",
  "email": "testuser01@example.com",
  "productId": "P1001",
  "quantity": -1
}
```

Expected:

```text id="znc2lw"
API should reject the invalid quantity.
```

---

## 11.4 Invalid Product ID

```json id="qv4n1y"
{
  "username": "testuser01",
  "email": "testuser01@example.com",
  "productId": "INVALID_PRODUCT",
  "quantity": 1
}
```

Expected:

```text id="hprzkt"
API should return an appropriate resource validation/error response.
```

---

# 12. API Boundary Data

| Data ID    | Field      |           Value | Condition         |
| ---------- | ---------- | --------------: | ----------------- |
| TD-API-001 | Quantity   |               0 | Minimum candidate |
| TD-API-002 | Quantity   |               1 | Valid             |
| TD-API-003 | Quantity   | Maximum allowed | Maximum boundary  |
| TD-API-004 | Quantity   |     Maximum + 1 | Above boundary    |
| TD-API-005 | Quantity   |              -1 | Negative          |
| TD-API-006 | Product ID |           Empty | Missing           |
| TD-API-007 | Product ID |         INVALID | Invalid           |

---

# 13. Special Character Data

The following values can be used to validate input handling:

```text id="jhhk1c"
!@#$%^&*()
<script>
' OR '1'='1
../../test
<test>
"test"
Test&QA
Test_User
Test-User
Test.User
```

These values are intended only for application validation and safe test environments.

---

# 14. Long Input Data

Example long text:

```text id="x0edh8"
This is a sample long input value created specifically for testing
maximum field length validation, UI behavior, database handling,
API request validation, and error handling without using real
customer information.
```

Use long values to validate:

* Maximum field length
* UI behavior
* API validation
* Database constraints
* Error messages
* Input truncation
* Application stability

---

# 15. Unicode Test Data

```text id="0n3vqt"
Test User
Chandan QA
测试用户
テストユーザー
Тестовый пользователь
```

Use Unicode values to validate:

* Internationalized input
* Character encoding
* UI rendering
* API handling
* Database storage

---

# 16. Empty and Null Data

| Data ID     | Field      | Value | Expected       |
| ----------- | ---------- | ----- | -------------- |
| TD-NULL-001 | Name       | Empty | Validation     |
| TD-NULL-002 | Email      | Empty | Validation     |
| TD-NULL-003 | Password   | Empty | Validation     |
| TD-NULL-004 | Product ID | Null  | API validation |
| TD-NULL-005 | Quantity   | Null  | API validation |
| TD-NULL-006 | Address    | Empty | Validation     |

---

# 17. Duplicate Data

Duplicate data can be used to validate:

* Duplicate account prevention
* Duplicate email validation
* Duplicate product entries
* Duplicate order prevention
* Duplicate payment prevention
* Duplicate API requests

Example:

| Data ID    | Data                      | Expected                    |
| ---------- | ------------------------- | --------------------------- |
| TD-DUP-001 | Existing email            | Registration rejected       |
| TD-DUP-002 | Existing wishlist product | Duplicate prevented         |
| TD-DUP-003 | Repeated order submission | One order created           |
| TD-DUP-004 | Repeated payment request  | Duplicate payment prevented |

---

# 18. Session Test Data

Session-related conditions:

| Data ID        | Condition             | Expected                                |
| -------------- | --------------------- | --------------------------------------- |
| TD-SESSION-001 | Active session        | User can access protected features      |
| TD-SESSION-002 | Expired session       | User redirected/authentication required |
| TD-SESSION-003 | Logged-out session    | Protected resource denied               |
| TD-SESSION-004 | Multiple browser tabs | Session handled consistently            |

---

# 19. Network Test Conditions

| Data ID    | Condition              | Expected                                          |
| ---------- | ---------------------- | ------------------------------------------------- |
| TD-NET-001 | Stable connection      | Normal operation                                  |
| TD-NET-002 | Slow connection        | Application remains usable or shows loading state |
| TD-NET-003 | Connection interrupted | Graceful error handling                           |
| TD-NET-004 | Connection restored    | Operation can recover where supported             |
| TD-NET-005 | API timeout            | Appropriate timeout/error handling                |

---

# 20. AI-Generated Test Data

Generative AI can assist with creating synthetic test data based on testing requirements.

Example prompt:

```text id="cl4zpu"
Generate synthetic test data for an E-Commerce registration
feature.

Include:
- Valid data
- Invalid email formats
- Boundary password values
- Missing mandatory fields
- Special characters
- Unicode values

Do not use real personal information.
Return the result in a structured table.
```

---

# 21. AI Test Data Validation

AI-generated data must be reviewed before use.

Validation criteria:

* [ ] Data matches the requirement.
* [ ] Data is syntactically valid where required.
* [ ] Invalid data is intentionally invalid.
* [ ] Boundary values are correct.
* [ ] Duplicate values are intentional.
* [ ] No real personal information is included.
* [ ] No real payment information is included.
* [ ] Data can be used repeatedly.
* [ ] Data does not introduce unsupported assumptions.

---

# 22. Data Privacy

This repository must not contain:

* Real customer names
* Real email addresses
* Real phone numbers
* Real addresses
* Real passwords
* Real credit/debit card numbers
* OTPs
* Authentication tokens
* API keys
* Access credentials
* Production database records

Only synthetic or publicly safe test data should be used.

---

# 23. Test Data Maintenance

Test data should be reviewed when:

* Application requirements change.
* Validation rules change.
* API contracts change.
* Product rules change.
* Checkout logic changes.
* New test scenarios are added.
* Existing defects require additional reproduction data.

---

# 24. Summary

The test data in this project provides coverage for:

* Registration
* Login
* Password validation
* Product search
* Product quantity
* Address management
* Checkout
* Payment
* API testing
* Boundary testing
* Negative testing
* Edge cases
* Unicode handling
* Special characters
* Session testing
* Network failure testing

Generative AI can accelerate test-data creation, but all generated data must be reviewed.

