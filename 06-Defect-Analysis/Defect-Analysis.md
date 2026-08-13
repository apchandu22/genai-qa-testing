# GenAI QA Testing - Defect Reports

## 1. Overview

This document contains sample defect reports demonstrating how defects can be documented, analyzed, prioritized, and validated during the QA lifecycle.

The defects are synthetic examples created for portfolio demonstration purposes.

---

## 2. Defect Report Format

| Field | Description |
|---|---|
| Defect ID | Unique defect identifier |
| Title | Short defect description |
| Module | Affected application module |
| Environment | Test environment |
| Preconditions | Required conditions |
| Steps to Reproduce | Steps to reproduce the issue |
| Expected Result | Expected application behavior |
| Actual Result | Actual application behavior |
| Severity | Impact of the defect |
| Priority | Fix urgency |
| Status | Current defect status |
| AI Assistance | How GenAI assisted |
| QA Validation | Human validation performed |

---

# 3. Defect Reports

## BUG-GENAI-001

### Title

Cart total is not updated after increasing product quantity.

### Module

Shopping Cart

### Environment

Test Environment

### Preconditions

- User is logged in.
- Product is available.
- Product has been added to the cart.

### Steps to Reproduce

1. Login to the application.
2. Add a product to the cart.
3. Open the shopping cart.
4. Increase the product quantity from 1 to 2.
5. Observe the cart total.

### Expected Result

The cart total should be recalculated based on the updated product quantity.

### Actual Result

The product quantity changes, but the cart total continues to display the previous amount.

### Severity

High

### Priority

High

### Status

Open

### AI Assistance

GenAI was used to analyze the reported behavior and suggest related regression scenarios.

### QA Validation

The defect was reviewed against the expected cart calculation behavior and reproduced in the test environment.

---

## BUG-GENAI-002

### Title

Invalid email format is accepted during registration.

### Module

Registration

### Environment

Test Environment

### Preconditions

Registration page is accessible.

### Steps to Reproduce

1. Open the registration page.
2. Enter a valid name.
3. Enter `invalid-email` in the email field.
4. Enter a valid password.
5. Submit the registration form.

### Expected Result

The application should reject the invalid email format and display a validation message.

### Actual Result

The registration form accepts the invalid email format.

### Severity

High

### Priority

High

### Status

Open

### AI Assistance

GenAI was used to identify additional invalid email formats and related validation scenarios.

### QA Validation

The generated scenarios were reviewed and relevant cases were added to the registration test suite.

---

## BUG-GENAI-003

### Title

Duplicate order is created when the Place Order button is clicked multiple times.

### Module

Order Management

### Environment

Test Environment

### Preconditions

- User is logged in.
- Cart contains a valid product.
- Checkout information is valid.

### Steps to Reproduce

1. Add a product to the cart.
2. Proceed to checkout.
3. Enter valid checkout information.
4. Click Place Order.
5. Quickly click Place Order again.

### Expected Result

Only one order should be created for the transaction.

### Actual Result

Multiple orders are created for the same transaction.

### Severity

Critical

### Priority

Critical

### Status

Open

### AI Assistance

GenAI was used to identify duplicate-submission and idempotency-related test scenarios.

### QA Validation

The suggested scenarios were reviewed and duplicate order prevention was added to regression coverage.

---

## BUG-GENAI-004

### Title

Logged-out user can access a previously visited protected page using browser Back navigation.

### Module

Authentication

### Environment

Test Environment

### Preconditions

User has successfully logged in.

### Steps to Reproduce

1. Login to the application.
2. Navigate to a protected page.
3. Logout.
4. Click the browser Back button.
5. Observe the protected page.

### Expected Result

The user should not be able to access protected information after logout.

### Actual Result

The previously loaded protected page is displayed.

### Severity

High

### Priority

High

### Status

Open

### AI Assistance

GenAI was used to suggest session-management and authentication regression scenarios.

### QA Validation

The behavior was evaluated from an access-control perspective and additional logout/session tests were identified.

---

## BUG-GENAI-005

### Title

Search returns irrelevant results for an unsupported search term.

### Module

Product Search

### Environment

Test Environment

### Test Data

```text
XYZUnknownProduct123

### Steps to Reproduce

1. Open the product search page.
2. Enter `XYZUnknownProduct123`.
3. Click Search.

### Expected Result

The application should display a clear no-results message.

### Actual Result

Irrelevant products are displayed.

### Severity

Medium

### Priority

Medium

### Status

Open

### AI Assistance

GenAI was used to generate negative search scenarios and search relevance test ideas.

### QA Validation

The search behavior was reviewed against the expected no-results behavior.

---

## BUG-GENAI-006

### Title

Payment failure incorrectly displays order confirmation.

### Module

Payment

### Environment

Test Environment

### Preconditions

- Valid order exists.
- Test payment method is configured to fail.

### Steps to Reproduce

1. Add a product to the cart.
2. Proceed to checkout.
3. Select a test payment method.
4. Trigger a payment failure.
5. Observe the order status.

### Expected Result

The payment should be marked as failed and the order should not be incorrectly confirmed.

### Actual Result

The payment fails, but the application displays an order confirmation.

### Severity

Critical

### Priority

Critical

### Status

Open

### AI Assistance

GenAI was used to identify payment failure, transaction consistency, and order-state validation scenarios.

### QA Validation

The defect was classified as critical because incorrect order confirmation can create business and financial impact.

---

# 4. AI-Assisted Defect Analysis

GenAI can assist QA Engineers during defect investigation.

### Example Prompt

```text
Act as a senior QA Engineer.

Analyze the following defect:

[Defect description]

Provide:

1. Possible defect category
2. Possible root causes
3. Additional reproduction scenarios
4. Regression areas
5. Suggested severity
6. Suggested priority

Clearly separate confirmed facts from hypotheses.
Do not claim a root cause without evidence.

# 5. Human Validation of AI Output

AI suggestions must be reviewed before being added to the defect report.

The QA Engineer validates:

- [ ] Reproduction steps
- [ ] Expected behavior
- [ ] Actual behavior
- [ ] Severity
- [ ] Priority
- [ ] Business impact
- [ ] Root-cause assumptions
- [ ] Regression scope

AI output is considered an assistant's recommendation, not a confirmed defect analysis.

---

# 6. Defect Severity Guidelines

| Severity | Description |
|---|---|
| Critical | Causes major business failure, data loss, security issue, or prevents core functionality |
| High | Major functionality is affected but the system remains partially usable |
| Medium | Functionality is affected but a workaround may exist |
| Low | Minor UI, cosmetic, or low-impact issue |

---

# 7. Defect Priority Guidelines

| Priority | Description |
|---|---|
| Critical | Immediate fix required |
| High | Fix before release where possible |
| Medium | Fix based on release scope |
| Low | Can be scheduled for a future release |

---

# 8. Defect Lifecycle

```text
New
 ↓
Assigned
 ↓
In Progress
 ↓
Fixed
 ↓
Retest
 ↓
Verified
 ↓
Closed


If the issue still exists:

Retest
 ↓
Failed
 ↓
Reopened
 ↓
Fixed

```md
# 9. Defect Quality Checklist

Before submitting a defect:

- [ ] Clear title
- [ ] Correct module
- [ ] Environment provided
- [ ] Preconditions defined
- [ ] Reproducible steps
- [ ] Expected result documented
- [ ] Actual result documented
- [ ] Severity assigned
- [ ] Priority assigned
- [ ] Supporting evidence available
- [ ] No unsupported root-cause claim
- [ ] Related regression areas identified

---

# 10. Summary

These defect reports demonstrate:

- Structured defect reporting
- Severity and priority classification
- Defect reproduction
- Negative testing
- Regression analysis
- AI-assisted investigation
- Human validation of AI-generated analysis
```

