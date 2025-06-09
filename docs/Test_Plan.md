# Test Plan - SecureInsure

## 1. Introduction
This Test Plan outlines the approach for testing the SecureInsure system, focusing on functionality and API security.

## 2. Objectives
- Ensure Web and App functionality (login, user management).
- Verify API security against CSRF and SQL Injection.

## 3. Scope
- **In Scope**: Functional testing (Web, App) and security testing (API).
- **Out of Scope**: Performance testing, mobile responsiveness.

## 4. Test Approach
- **Type**: Manual Testing.
- **Tools**: Postman, OWASP ZAP.
- **Environment**: Localhost (XAMPP, MySQL), Windows 11.

## 5. Test Cases
- Total: 32 test cases (4 Web, 25 App, 3 API).
- Criteria: Pass if actual result matches expected result.

## 6. Resources
- Tester: Alexia Viet (Cẩm Tú).
- Duration: 2 weeks, May 2025.

## 7. Risks
- Token refresh errors in App may cause test failures.

## 8. Deliverables
- Test cases: [API_Testing.md](Test_Cases/API_Testing.md)
- Screenshots: [OWASP ZAP](Screenshots/OWASP_Screenshots)