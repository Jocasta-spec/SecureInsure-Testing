# Test Plan Execution Report - SecureInsure-Testing Project

**Date**: May 26, 2025   
**Author**: Group Project (2 Members)  
**Supervisor**: MSc. Võ Ngọc Tấn Phước  

## Summary

| Metric          | Value |
|-----------------|-------|
| Test Plans      | 1     |
| Test Cases      | 34    |
| Pass            | 28    |
| Fail            | 6     |

**Test Case execution progress**: 100% completed

## Test Case Details

### 5.1. Yêu cầu tài nguyên kiểm thử
- **Phần cứng**: PC có internet.
- **Phần mềm**: XAMPP, Chrome, Postman, Java JDK, Maven.

### 5.2. Danh sách các tình huống kiểm thử

| ID trường hợp thử nghiệm | Mô tả trường hợp thử nghiệm                     | Trạng thái (P/F) | Số lỗi |
|--------------------------|------------------------------------------------|--------------------|--------|
| TC_CUSTOMER_WEB_LOGIN_01  | Đăng nhập thành công với tài khoản Customer qua /login | P                 | 0      |
| TC_CUSTOMER_WEB_LOGIN_02  | Đăng nhập thất bại với tài khoản Customer bị chặn qua /login | P                 | 0      |
| TC_ADMIN_WEB_ADDUSER_01   | Thêm Admin mới thành công                      | P                 | 0      |
| TC_ADMIN_WEB_ADDUSER_02   | Thêm Admin với email đã tồn tại                | P                 | 0      |
| TC_ADMIN_WEB_EDITUSER_01  | Sửa thông tin Khách hàng thành công            | P                 | 0      |
| TC_ADMIN_WEB_DELETEUSER_01| Xóa Khách hàng thành công                     | P                 | 0      |
| TC_LOGIN_APP_01           | Đăng nhập qua App với user không tồn tại (Lần 1) | F                 | 1      |
| TC_LOGIN_APP_02           | Đăng nhập qua App với user không tồn tại (Lần 2) | P                 | 0      |
| TC_LOGIN_APP_03           | Đăng nhập qua App với user admin bị chặn (Lần 1) | F                 | 1      |
| TC_LOGIN_APP_04           | Đăng nhập qua App với user admin bị chặn (Lần 2) | P                 | 0      |
| TC_ROLE_APP_01            | Phân quyền truy cập TaskPanel (Lần 1)          | F                 | 1      |
| TC_ROLE_APP_02            | Phân quyền truy cập TaskPanel (Lần 2)          | F                 | 1      |
| TC_ROLE_APP_03            | Phân quyền truy cập TaskPanel (Lần 3)          | P                 | 0      |
| TC_GETUSER_APP_01         | Hiển thị danh sách người dùng trên TaskPanel (Lần 1) | F                 | 1      |
| TC_GETUSER_APP_02         | Hiển thị danh sách người dùng trên TaskPanel (Lần 2) | F                 | 1      |
| TC_GETUSER_APP_03         | Hiển thị danh sách người dùng trên TaskPanel (Lần 3) | P                 | 0      |
| TC_ADDUSER_APP_01         | Thêm người dùng mới trên TaskPanel (Lần 1)     | F                 | 1      |
| TC_ADDUSER_APP_02         | Thêm người dùng mới trên TaskPanel (Lần 2)     | F                 | 1      |
| TC_ADDUSER_APP_03         | Thêm người dùng mới trên TaskPanel (Lần 3)     | P                 | 0      |
| TC_ADDUSER_APP_04         | Thêm người dùng với email đã tồn tại (Lần 1)   | F                 | 1      |
| TC_ADDUSER_APP_04         | Thêm người dùng với email đã tồn tại (Lần 2)   | P                 | 0      |
| TC_DELETEUSER_APP_01      | Xóa người dùng trên TaskPanel (Lần 1)          | F                 | 1      |
| TC_DELETEUSER_APP_02      | Xóa người dùng trên TaskPanel (Lần 2)          | F                 | 1      |
| TC_DELETEUSER_APP_03      | Xóa người dùng trên TaskPanel (Lần 3)          | P                 | 0      |
| TC_UPDATEUSER_APP_01      | Sửa thông tin người dùng trên TaskPanel (Lần 1)| F                 | 1      |
| TC_UPDATEUSER_APP_02      | Sửa thông tin người dùng trên TaskPanel (Lần 2)| F                 | 1      |
| TC_UPDATEUSER_APP_03      | Sửa thông tin người dùng trên TaskPanel (Lần 3)| P                 | 0      |
| TC_LOGOUT_APP_01          | Đăng xuất và quay lại màn hình đăng nhập (Lần 1)| F                 | 1      |
| TC_LOGOUT_APP_02          | Đăng xuất và quay lại màn hình đăng nhập (Lần 2)| F                 | 1      |
| TC_LOGOUT_APP_03          | Đăng xuất và quay lại màn hình đăng nhập (Lần 3)| P                 | 0      |
| TC_Token_Stored_01        | Kiểm tra token trong thư mục tokens được mã hóa| P                 | 0      |
| TC_API_Secu_01            | Kiểm tra yêu cầu CSRF token trên endpoint /add | P                 | 0      |
| TC_API_Secu_02            | Kiểm tra POST request tới /add với CSRF token hợp lệ | P                 | 0      |
| TC_API_Secu_03            | Kiểm tra chống SQL Injection trên /AdminUpdate | -                 | 0      |

## Conclusion
All 34 test cases have been executed. Out of these, 28 passed, and 6 failed. The failed cases (TC_LOGIN_APP_01, TC_LOGIN_APP_03, TC_ROLE_APP_01, TC_ROLE_APP_02, TC_GETUSER_APP_01, TC_GETUSER_APP_02, TC_ADDUSER_APP_01, TC_ADDUSER_APP_02, TC_ADDUSER_APP_04 (Lần 1), TC_DELETEUSER_APP_01, TC_DELETEUSER_APP_02, TC_UPDATEUSER_APP_01, TC_UPDATEUSER_APP_02, TC_LOGOUT_APP_01, TC_LOGOUT_APP_02) require further debugging and fixes. TC_API_Secu_03 needs additional verification for SQL Injection security.
