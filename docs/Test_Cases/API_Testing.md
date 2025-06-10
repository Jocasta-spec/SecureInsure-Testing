# API Testing Documentation

Overview: This document contains test cases for testing the SecureInsure API, focusing on security vulnerabilities such as CSRF, SQL Injection, and XSS. Tests were performed using Postman and OWASP ZAP.

## Test Case List

### 1. API Functional and Security Test Cases (Postman & OWASP ZAP)
| ID              | Description                              | Steps                                                                 | Test Data                            | Expected Result                            | Actual Result                              | Pass/Fail |
|-----------------|------------------------------------------|----------------------------------------------------------------------|--------------------------------------|--------------------------------------------|--------------------------------------------|-----------|
| TC_API_Secu_01  | Kiểm tra CSRF token trên /add            | 1. Gửi POST request tới http://localhost/API_Secu/add không kèm CSRF token using Postman.<br>2. Kiểm tra response.<br>3. Verify với OWASP ZAP Active Scan. | Email: testuser1@gmail.com           | Response: "403 Forbidden - CSRF token missing" | Response: "403 Forbidden - CSRF token missing" | Pass      |
| TC_API_Secu_02  | POST /add với CSRF token hợp lệ          | 1. Gửi POST request tới http://localhost/API_Secu/add với CSRF token hợp lệ using Postman.<br>2. Kiểm tra response.<br>3. Verify không có lỗi CSRF với OWASP ZAP. | Email: testuser1@gmail.com<br>CSRF: valid_token | Response: "Thêm người dùng thành công"     | Response: "Thêm người dùng thành công"     | Pass      |
| TC_API_Secu_03  | Chống SQL Injection trên /AdminUpdate    | 1. Gửi POST request tới http://localhost/API_Secu/AdminUpdate với dữ liệu SQL Injection using Postman.<br>2. Kiểm tra response.<br>3. Run OWASP ZAP Active Scan để xác nhận không có lỗ hổng. | Role: "' OR '1'='1"                  | Response: "Cập nhật thành công" (no exploit) | Response: "Cập nhật thành công" (no exploit) | Pass      |

### 2. OWASP ZAP Security Test Cases
| ID              | Description                              | Steps                                                                 | Test Data                            | Expected Result                            | Actual Result                              | Pass/Fail |
|-----------------|------------------------------------------|----------------------------------------------------------------------|--------------------------------------|--------------------------------------------|--------------------------------------------|-----------|
| TC_ZAP_01       | Scan CSRF vulnerability trên /add         | 1. Mở OWASP ZAP, cấu hình proxy cho http://localhost/API_Secu.<br>2. Chạy Active Scan trên endpoint /add.<br>3. Gửi POST request không kèm CSRF token qua OWASP ZAP Manual Explore.<br>4. Kiểm tra Alerts tab. | None                                 | OWASP ZAP báo "CSRF token missing" trong Alerts tab. Sau khi fix, không có CSRF alerts. | Ban đầu báo lỗi CSRF. Fix bằng CSRF token validation. Không có alerts sau fix. | Pass      |
| TC_ZAP_02       | Scan SQL Injection trên /AdminUpdate     | 1. Cấu hình OWASP ZAP cho http://localhost/API_Secu/AdminUpdate.<br>2. Chạy Active Scan với SQL Injection payloads.<br>3. Kiểm tra Alerts tab.<br>4. Re-scan sau khi áp dụng prepared statements. | Input: "role=' OR '1'='1"            | OWASP ZAP không báo lỗi SQL Injection sau fix. | Ban đầu báo nguy cơ SQL Injection. Fix bằng prepared statements. Không có alerts sau fix. | Pass      |
| TC_ZAP_03       | Scan XSS vulnerability trên /add         | 1. Cấu hình OWASP ZAP cho http://localhost/API_Secu/add.<br>2. Chạy Active Scan với XSS payloads.<br>3. Gửi POST request với payload XSS qua OWASP ZAP Manual Explore.<br>4. Kiểm tra Alerts tab. | Input: "<script>alert('xss')</script>" | OWASP ZAP không báo lỗi XSS sau khi sanitizing inputs. | Không có XSS alerts sau khi sanitizing inputs. | Pass      |

## Notes
- **Tools Used**: Postman for API functional testing, OWASP ZAP (v2.12) for security scanning.
- **Environment**: Localhost (XAMPP, MySQL), tested in May 2025.
- **Fixes Implemented**: CSRF token validation, prepared statements, input sanitization.
- **Screenshots**: [OWASP ZAP](docs/Screenshots/OWASP_Screenshots/zap_csrf_alert.png)
