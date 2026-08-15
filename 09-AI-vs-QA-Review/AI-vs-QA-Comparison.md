# AI-Generated vs QA-Reviewed Test Cases

## 1. Purpose

This document demonstrates the difference between raw Generative AI output and the final test design after review by a QA Engineer.

## 2. Comparison

| Area | AI-Generated Output | QA-Reviewed Output |
|---|---|---|
| Login | Covers valid username/password | Adds empty fields, locked user, invalid format, session and boundary cases |
| API POST | Covers valid request | Adds missing fields, invalid types, duplicate data, authorization and schema checks |
| Payment | Covers successful payment | Adds timeout, retry, duplicate transaction, cancellation and failure recovery |
| Search | Covers valid keyword | Adds empty search, special characters, long input, case sensitivity and no-result scenarios |
| Defect Analysis | Summarizes reported behavior | Verifies evidence, reproduction, impact, priority and additional investigation |

## 3. QA Review Checklist

Before accepting AI-generated test cases, the QA Engineer validates:

- Requirement traceability
- Business-rule accuracy
- Positive and negative coverage
- Boundary and edge cases
- Security and authorization scenarios
- Test data quality
- Expected-result accuracy
- Duplicate scenarios
- Risk and priority
- Testability

## 4. Key Learning

GenAI is most effective as a **test-design accelerator**, not as an autonomous QA decision maker. The final test suite should be requirement-driven and reviewed by a human tester.

## 5. Portfolio Note

All examples are synthetic and created for demonstration and learning purposes.
