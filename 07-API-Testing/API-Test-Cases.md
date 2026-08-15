# API Test Cases — GenAI-Assisted QA

## 1. Objective

This document demonstrates how Generative AI can assist a QA Engineer in designing REST API test coverage. All examples use synthetic data and are intended for portfolio demonstration.

## 2. API Coverage

| ID | Test Area | Validation |
|---|---|---|
| API-001 | GET request | Successful response and schema |
| API-002 | POST request | Valid request creates resource |
| API-003 | PUT request | Existing resource is updated |
| API-004 | DELETE request | Resource is deleted successfully |
| API-005 | Required fields | Missing mandatory field validation |
| API-006 | Invalid data | Incorrect data type / format handling |
| API-007 | Authentication | Unauthorized request handling |
| API-008 | Authorization | Access-control validation |
| API-009 | Status codes | 2xx, 4xx and 5xx validation |
| API-010 | Response time | Basic response-time validation |
| API-011 | JSON schema | Required fields and data types |
| API-012 | Boundary values | Minimum, maximum and empty values |

## 3. Detailed Test Cases

### API-001 — GET Resource with Valid ID
**Precondition:** Valid resource exists.

**Steps:**
1. Send GET request with a valid resource ID.
2. Verify HTTP status code.
3. Validate response body.
4. Validate required JSON fields.

**Expected Result:** API returns `200 OK` and the expected resource details with valid field types.

**Priority:** High

### API-002 — Create Resource with Valid Payload
**Steps:**
1. Send POST request with all mandatory fields and valid values.
2. Verify response status.
3. Validate generated resource ID.
4. Validate response body.

**Expected Result:** API returns `201 Created` and the newly created resource information.

**Priority:** High

### API-003 — Update Existing Resource
**Steps:**
1. Send PUT request for an existing resource.
2. Change one or more valid fields.
3. Verify response status.
4. Retrieve the resource using GET.

**Expected Result:** API returns a successful update response and GET confirms the updated values.

**Priority:** High

### API-004 — Delete Existing Resource
**Steps:**
1. Send DELETE request for a valid resource.
2. Verify response status.
3. Attempt GET for the deleted resource.

**Expected Result:** Resource is deleted successfully and subsequent retrieval returns the appropriate not-found response.

**Priority:** Medium

### API-005 — Missing Mandatory Field
**Steps:**
1. Remove a required field from a POST request.
2. Send the request.
3. Validate status code and error response.

**Expected Result:** API rejects the request with an appropriate `4xx` response and a clear validation message.

**Priority:** High

### API-006 — Invalid Data Type
**Steps:**
1. Provide an invalid data type for a numeric, date or boolean field.
2. Send the request.
3. Validate the error response.

**Expected Result:** API rejects invalid input without creating or modifying data.

**Priority:** High

### API-007 — Missing Authentication
**Steps:**
1. Remove the authentication token/header.
2. Send a protected endpoint request.

**Expected Result:** API rejects the request with the appropriate unauthorized response, such as `401 Unauthorized`.

**Priority:** Critical

### API-008 — Unauthorized Resource Access
**Steps:**
1. Authenticate as User A.
2. Attempt to access a resource belonging to User B.
3. Validate the response.

**Expected Result:** API denies access and does not expose protected information.

**Priority:** Critical

### API-009 — HTTP Status Code Validation

Validate appropriate status codes for successful, invalid, unauthorized, forbidden and not-found conditions.

**Expected Result:** Status codes accurately represent the outcome and follow the API contract.

**Priority:** High

### API-010 — Response Time Validation
**Steps:**
1. Execute the endpoint with representative test data.
2. Capture response time.
3. Repeat under normal test conditions.

**Expected Result:** Response time meets the agreed API performance threshold.

**Priority:** Medium

### API-011 — JSON Schema Validation

Validate required fields, field names, data types, nullability, nested objects and array structure.

**Expected Result:** Response matches the expected contract/schema.

**Priority:** High

### API-012 — Boundary Value Validation

Test minimum, maximum, empty and near-boundary values for applicable fields.

**Expected Result:** API accepts valid boundary values and rejects values outside defined business rules.

**Priority:** High

## 4. GenAI QA Review Checklist

AI-generated API cases are reviewed by the QA Engineer for:

- Requirement coverage
- Authentication and authorization coverage
- Positive and negative scenarios
- Boundary conditions
- Correct status codes
- Response schema validation
- Data integrity
- Security-sensitive cases
- Duplicate test cases
- Business-rule accuracy

## 5. Tools

- Postman
- REST API
- JSON
- SQL / MySQL
- JIRA
- Generative AI / Prompt Engineering

> **Note:** These are synthetic portfolio examples and do not represent confidential production APIs or customer data.
