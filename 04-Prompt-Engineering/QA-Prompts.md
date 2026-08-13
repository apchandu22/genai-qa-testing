# GenAI QA Testing - QA Prompt Engineering

## 1. Overview

This document contains reusable prompts designed for common Software Quality Assurance activities.

The prompts demonstrate how Generative AI can be used to assist QA Engineers with:

* Requirement analysis
* Test scenario generation
* Test case generation
* Negative testing
* Boundary testing
* Edge-case identification
* Test data generation
* API testing
* Defect analysis
* Regression testing
* Test coverage analysis
* Test case optimization

AI-generated outputs must always be reviewed and validated by a QA Engineer before being used as final testing artifacts.

---

# 2. Prompt Engineering Principles

Effective QA prompts should provide:

1. Clear context
2. Application or feature information
3. Testing objective
4. Relevant constraints
5. Expected output format
6. Testing technique
7. Business rules where applicable

A good prompt should minimize ambiguity and encourage the AI model to produce structured and testable results.

---

# 3. Requirement Analysis Prompt

### Prompt

```text
You are a senior QA Engineer.

Analyze the following software requirement.

Requirement:
[Paste requirement here]

Identify:
1. Functional requirements
2. Business rules
3. Mandatory validations
4. Positive scenarios
5. Negative scenarios
6. Boundary conditions
7. Edge cases
8. Integration points
9. Potential risks
10. Missing or ambiguous requirements

Return the results in a structured table.
Do not make unsupported assumptions.
Clearly identify any assumptions separately.
```

### Purpose

Used to analyze requirements before creating test scenarios.

---

# 4. Test Scenario Generation Prompt

### Prompt

```text
Act as an experienced Software QA Engineer.

Application:
E-Commerce Web Application

Feature:
[Feature name]

Requirement:
[Requirement]

Generate comprehensive test scenarios covering:

- Positive scenarios
- Negative scenarios
- Boundary conditions
- Edge cases
- Validation scenarios
- Business rules
- Error handling
- Integration scenarios

Assign:
- Scenario ID
- Scenario description
- Scenario type
- Priority

Avoid duplicate scenarios and clearly identify assumptions.
```

### Purpose

Used to generate an initial set of test scenarios.

---

# 5. Test Case Generation Prompt

### Prompt

```text
Act as a senior QA Engineer.

Convert the following test scenario into a detailed execution-ready test case.

Scenario:
[Scenario]

Provide:

- Test Case ID
- Scenario ID
- Module
- Test case description
- Preconditions
- Test data
- Detailed steps
- Expected result
- Priority
- Test type

Ensure every step has a clear and measurable expected result.
Do not invent application behavior that is not supported by the requirement.
```

### Purpose

Used to convert high-level scenarios into executable test cases.

---

# 6. Negative Test Case Prompt

### Prompt

```text
You are a QA Engineer specializing in negative testing.

Feature:
[Feature]

Requirement:
[Requirement]

Identify negative test cases covering:

- Invalid input
- Missing input
- Incorrect format
- Special characters
- Invalid combinations
- Unauthorized access
- Duplicate requests
- Unexpected user actions
- Server errors
- Network failures
- Session expiration

For each case provide:
Test Case ID
Condition
Test Data
Steps
Expected Result
Priority
```

### Purpose

Used to improve negative test coverage.

---

# 7. Boundary Value Analysis Prompt

### Prompt

```text
Act as a senior QA Engineer.

Analyze the following field requirement:

Field:
[Field name]

Requirement:
[Minimum / Maximum / Allowed range]

Generate Boundary Value Analysis test cases covering:

- Below minimum
- Minimum
- Minimum + 1
- Normal value
- Maximum - 1
- Maximum
- Above maximum

Provide the test data and expected result for each condition.
```

### Purpose

Used to identify boundary-related defects.

---

# 8. Equivalence Partitioning Prompt

### Prompt

```text
Analyze the following input requirement using Equivalence Partitioning.

Field:
[Field]

Requirement:
[Requirement]

Identify:
1. Valid equivalence partitions
2. Invalid equivalence partitions
3. Representative test data for each partition
4. Expected behavior

Present the output in a structured table.
```

### Purpose

Used to reduce redundant testing while maintaining coverage.

---

# 9. Edge Case Generation Prompt

### Prompt

```text
Act as an experienced exploratory tester.

Feature:
[Feature]

Identify uncommon but realistic edge cases that could cause defects.

Consider:

- Empty values
- Null values
- Very large values
- Very small values
- Special characters
- Unicode characters
- Long input
- Duplicate actions
- Rapid repeated actions
- Network interruption
- Session expiration
- Browser refresh
- Back button
- Multiple tabs
- Concurrent actions
- Unexpected user behavior

For each edge case provide:
Condition
Steps
Expected Result
Risk
Priority
```

### Purpose

Used to identify scenarios that may not be obvious from normal requirements.

---

# 10. Test Data Generation Prompt

### Prompt

```text
Generate test data for an E-Commerce application.

Create data for:

- User registration
- Login
- Product search
- Product quantity
- Address
- Checkout
- API requests

Provide:
- Valid data
- Invalid data
- Boundary data
- Negative data
- Special-character data

Do not use real personal information.

Return the data in a structured table suitable for QA testing.
```

### Purpose

Used to generate safe and reusable test data.

---

# 11. API Test Scenario Prompt

### Prompt

```text
Act as an API Testing specialist.

API:
[Endpoint]

HTTP Method:
[GET / POST / PUT / DELETE]

Request:
[Request details]

Generate API test scenarios covering:

- Valid request
- Invalid request
- Missing parameters
- Invalid parameters
- Authentication
- Authorization
- Status codes
- Headers
- Response body
- JSON schema
- Boundary values
- Duplicate requests
- Error handling

Provide:
Test Scenario ID
Scenario
Request
Expected Status Code
Expected Response
Priority
```

### Purpose

Used to generate API test coverage.

---

# 12. API Test Case Prompt

### Prompt

```text
Create detailed API test cases for the following API.

Endpoint:
[Endpoint]

Method:
[Method]

Request:
[Request]

Expected behavior:
[Requirement]

Include:

1. Positive test
2. Negative test
3. Missing parameter test
4. Invalid parameter test
5. Authentication test
6. Authorization test
7. Status code validation
8. Response body validation
9. Header validation
10. Error response validation

Provide test cases in a structured format.
```

---

# 13. Defect Analysis Prompt

### Prompt

```text
Act as a senior QA Engineer assisting with defect analysis.

Defect:
[Defect description]

Steps to reproduce:
[Steps]

Expected Result:
[Expected]

Actual Result:
[Actual]

Analyze:

1. Possible defect category
2. Possible root causes
3. Additional information required
4. Related areas to investigate
5. Additional test scenarios
6. Regression areas
7. Suggested severity
8. Suggested priority

Do not claim a root cause as confirmed unless sufficient evidence is provided.
Clearly separate facts from hypotheses.
```

### Purpose

Used to assist investigation while avoiding unsupported root-cause claims.

---

# 14. Regression Test Selection Prompt

### Prompt

```text
Act as a QA Engineer.

The following change has been implemented:

Change:
[Change description]

Affected module:
[Module]

Identify the regression testing scope.

Consider:
- Directly affected functionality
- Dependent functionality
- Integration points
- End-to-end workflows
- Previously defect-prone areas
- Critical business workflows

Return:
Test Area
Regression Scenario
Reason
Priority
```

---

# 15. Test Case Review Prompt

### Prompt

```text
Review the following test case as a senior QA reviewer.

Test Case:
[Paste test case]

Check for:

- Requirement coverage
- Clear preconditions
- Complete test data
- Executable steps
- Measurable expected results
- Duplicate coverage
- Missing negative scenarios
- Missing boundary conditions
- Incorrect assumptions
- Priority accuracy

Provide:
1. Issues found
2. Recommended changes
3. Improved test case
```

---

# 16. Test Case Optimization Prompt

### Prompt

```text
Review the following list of test cases.

Identify:

- Duplicate test cases
- Similar test cases
- Missing coverage
- Unnecessary cases
- High-risk missing scenarios
- Opportunities to combine cases without reducing coverage

Return:

Original Test Case
Recommendation
Reason
Final Action
```

### Purpose

Used to improve test suite efficiency.

---

# 17. Requirement-to-Test Traceability Prompt

### Prompt

```text
Create a Requirement Traceability Matrix for the following requirements and test cases.

Requirements:
[Requirements]

Test Cases:
[Test Cases]

Map each requirement to one or more test cases.

Identify:
- Covered requirements
- Partially covered requirements
- Uncovered requirements
- Duplicate coverage

Return:
Requirement ID
Requirement
Test Case IDs
Coverage Status
Comments
```

---

# 18. Test Coverage Analysis Prompt

### Prompt

```text
Analyze the following test scenarios and test cases.

Identify coverage for:

- Functional requirements
- Positive scenarios
- Negative scenarios
- Boundary conditions
- Edge cases
- Business rules
- Integration points
- Error handling

Identify gaps and recommend additional test scenarios.

Do not assume that a feature is covered simply because a related test exists.
```

---

# 19. Exploratory Testing Prompt

### Prompt

```text
Act as an experienced exploratory tester.

Feature:
[Feature]

Create an exploratory testing charter containing:

- Testing objective
- Areas to explore
- Risks
- Test ideas
- User behaviors
- Error conditions
- Data variations
- Browser/device considerations
- Questions to investigate

Focus on discovering unexpected defects rather than repeating scripted test cases.
```

---

# 20. User Journey Testing Prompt

### Prompt

```text
Analyze the following E-Commerce user journey:

Login → Search Product → Product Details → Add to Cart → Checkout → Payment → Order Confirmation

Identify:

- Happy path
- Alternate paths
- Negative paths
- Failure points
- Integration risks
- Session risks
- Payment risks
- Data consistency risks
- Recovery scenarios

Prioritize the scenarios based on business impact.
```

---

# 21. Defect Reproduction Prompt

### Prompt

```text
Analyze the following defect report.

Defect:
[Description]

Environment:
[Environment]

Steps:
[Steps]

Expected:
[Expected result]

Actual:
[Actual result]

Suggest additional reproduction steps and test conditions that may help reproduce the issue.

Do not modify the reported facts.
Clearly separate suggestions from confirmed observations.
```

---

# 22. SQL Validation Prompt

### Prompt

```text
Act as a QA Engineer with SQL testing experience.

Requirement:
[Requirement]

Identify database validation scenarios for the feature.

Consider:

- Data insertion
- Data update
- Data deletion
- Data consistency
- Null values
- Duplicate records
- Referential relationships
- Transaction consistency

Provide:
Scenario
SQL validation objective
Expected database result
Priority
```

---

# 23. Prompt for Test Summary Report

### Prompt

```text
Act as a QA Lead.

Analyze the following test execution results:

Total Test Cases:
[Total]

Passed:
[Passed]

Failed:
[Failed]

Blocked:
[Blocked]

Defects:
[Defects]

Generate a professional test summary report containing:

- Test execution summary
- Pass percentage
- Failure summary
- Defect summary
- Major risks
- Regression status
- Release recommendation

Do not invent missing information.
```

---

# 24. Prompt Quality Checklist

Before using a QA prompt, verify:

* [ ] Application context is provided.
* [ ] Feature is clearly identified.
* [ ] Requirement is provided.
* [ ] Testing objective is clear.
* [ ] Required output format is specified.
* [ ] Testing technique is identified where applicable.
* [ ] Business constraints are included.
* [ ] Assumptions are controlled.
* [ ] AI is instructed not to invent unsupported behavior.
* [ ] Output will be reviewed by a QA Engineer.

---

# 25. AI Output Validation Checklist

AI output should be reviewed for:

* [ ] Accuracy
* [ ] Requirement alignment
* [ ] Business relevance
* [ ] Duplicate scenarios
* [ ] Missing scenarios
* [ ] Incorrect assumptions
* [ ] Invalid test data
* [ ] Incorrect expected results
* [ ] Incorrect priority
* [ ] Security concerns
* [ ] Privacy concerns
* [ ] Testability

---

# 26. Human-in-the-Loop Approach

The GenAI QA workflow follows:

```text
Requirement
     ↓
QA Analysis
     ↓
Prompt Design
     ↓
GenAI Output
     ↓
QA Review
     ↓
Correction / Enhancement
     ↓
Approved Test Artifact
     ↓
Test Execution
     ↓
Defect Analysis
```

Generative AI is treated as an assistant throughout this process.

The QA Engineer remains responsible for the final quality and accuracy of all testing artifacts.

---

# 27. Prompt Engineering Best Practices

### Be Specific

Instead of:

```text
Generate test cases for login.
```

Use:

```text
Act as a senior QA Engineer. Generate functional, negative,
boundary, and security-related test cases for an E-Commerce
login feature. Include test data, steps, expected results,
priority, and test type.
```

### Provide Context

AI output becomes more useful when the application, feature, requirements, and expected behavior are clearly described.

### Define the Output

Specify whether the result should be:

* Table
* Test case format
* Scenario list
* Defect analysis
* JSON
* Markdown

### Control Assumptions

Prompts should instruct the AI to clearly identify assumptions rather than silently inventing application behavior.

### Review Before Use

AI-generated output must be reviewed against the actual requirements and application behavior.

---

# 28. Final Conclusion

Prompt engineering is an important part of effective GenAI-assisted QA.

Well-designed prompts can help QA Engineers:

* Reduce repetitive test design effort
* Identify additional test scenarios
* Improve negative test coverage
* Generate test data
* Analyze defects
* Optimize regression suites
* Improve requirement traceability
* Accelerate documentation


