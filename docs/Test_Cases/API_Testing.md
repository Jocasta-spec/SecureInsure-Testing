# API Testing Documentation

## Overview
This document contains test cases for testing the SecureInsure API, focusing on security vulnerabilities such as CSRF, SQL Injection, and XSS. Tests were performed using Postman and OWASP ZAP.

## Test Case List

### 1. API Functional and Security Test Cases (Postman & OWASP ZAP)
| ID              | Description                              | Steps                                                                 | Test Data                            | Expected Result                            | Actual Result                              | Pass/Fail |
|-----------------|------------------------------------------|----------------------------------------------------------------------|--------------------------------------|--------------------------------------------|--------------------------------------------|-----------|
| TC_API_Secu_01  | Kiểm tra CSRF token trên /add            | 1. Gửi POST request tới http://localhost/API_Secu/add không kèm CSRF token using Postman.<br>2. Kiểm tra response.<br>3. Verify với OWASP ZAP Active Scan. | Email: testuser1@gmail.com           | Response: "403 Forbidden - CSRF token missing" | Response: "403 Forbidden - CSRF token missing" | Pass      |
| TC_API_Secu_02  | POST /add với CSRF token hợp lệ          | 1. Gửi POST request tới http://localhost/API_Secu/add với CSRF token hợp lệ using Postman.<br>2. Kiểm tra response.<br>3. Verify không có lỗi CSRF với OWASP ZAP. | Email: testuser1@gmail.com<br>CSRF: valid_token | Response: "Thêm người dùng thành công"     | Response: "Thêm người dùng thành công"     | Pass      |
| TC_API_Secu_03  | Chống SQL Injection trên /AdminUpdate    | 1. Gửi POST request tới http://localhost/API_Secu/AdminUpdate với dữ liệu SQL Injection using Postman.<br>2. Kiểm tra response.<br>3. Run OWASP ZAP Active Scan để xác nhận không có lỗ hổng. | Role: "' OR '1'='1"                  | Response: "Cập nhật thành công" (no exploit) | Response: "Cập nhật thành công" (no exploit) | Pass      |

### 2. Kiểm thử bằng OWASP ZAP

#### Quy trình kiểm thử
- **Mục tiêu**: Kiểm tra bảo mật các endpoint của API (/API_Secu) để phát hiện các lỗ hổng tiềm ẩn.
- **Công cụ**: OWASP ZAP kết hợp với Postman.
- **Các bước thực hiện**:
  1. Cấu hình Postman sử dụng proxy của OWASP ZAP:
     - Trong Postman: **Settings** > **Proxy** > Đặt proxy là `localhost` và port `8081`.
     - Đảm bảo ZAP đang chạy và lắng nghe trên port `8081`.
  2. Chạy tất cả các endpoint trong Postman:
     - Gửi các request GET, POST với dữ liệu mẫu (VD: email, role).
     - ZAP tự động ghi nhận các request và response.
  3. Thực hiện Spider:
     - Trong ZAP, nhấp chuột phải vào site `http://localhost/API_Secu` > **Attack** > **Spider** > **Start Scan** để khám phá các liên kết và tài nguyên.
  4. Thực hiện Active Scan:
     - Nhấp chuột phải vào `http://localhost/API_Secu` > **Attack** > **Active Scan** > **Start Scan** để kiểm tra các lỗ hổng bảo mật.
  5. Ghi lại kết quả:
     - Kiểm tra tab **Alerts** để liệt kê các lỗi phát hiện (VD: SQL Injection, Directory Browsing).
     - Chụp ảnh màn hình các lỗi và lưu vào thư mục `Screenshots/OWASP_Screenshots/`.

## Notes
- **Tools Used**: Postman for API functional testing, OWASP ZAP (v2.12) for security scanning.
- **Environment**: Localhost (XAMPP, MySQL), tested in May 2025.
- **Fixes Implemented**: CSRF token validation, prepared statements, input sanitization.
- **Screenshots**: [OWASP ZAP](docs/Screenshots/OWASP_Screenshots/zap_csrf_alert.png)
