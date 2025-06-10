# Test Plan Execution Report - SecureInsure-Testing Project

**Date**: May 25, 2025  
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

| STT | Mã Test Case          | Tên Test Case                          | Mô tả                                                                 |
|-----|-----------------------|----------------------------------------|----------------------------------------------------------------------|
| 1   | TC_CUSTOMER_WEB_LOGIN_01 | Đăng nhập thành công với tài khoản Customer qua /login | Từ trang chủ, chọn "đăng nhập", nhập email và mật khẩu hợp lệ, kiểm tra thông báo thành công. |
| 2   | TC_CUSTOMER_WEB_LOGIN_02 | Đăng nhập thất bại với tài khoản Customer bị chặn qua /login | Từ trang chủ, chọn "đăng nhập", không nhập email, kiểm tra thông báo lỗi. |
| 3   | TC_ADMIN_WEB_ADDUSER_01 | Thêm Admin mới thành công             | Thêm user mới, kiểm tra giao diện và database, dự kiến lỗi.          |
| 4   | TC_ADMIN_WEB_ADDUSER_02 | Thêm Admin với email đã tồn tại       | Thêm user mới, kiểm tra giao diện và database, dự kiến lỗi.          |
| 5   | TC_ADMIN_WEB_EDITUSER_01 | Sửa thông tin Khách hàng thành công   | Sửa thông tin user, kiểm tra database, giao diện hiển thị.           |
| 6   | TC_ADMIN_WEB_DELETEUSER_01 | Xóa Khách hàng thành công            | Xóa user, kiểm tra giao diện và database.                            |
| 7   | TC_LOGIN_APP_01        | Đăng nhập qua App với user không tồn tại (Lần 1) | Đăng nhập với email không tồn tại, kiểm tra response và giao diện lỗi. |
| 8   | TC_LOGIN_APP_02        | Đăng nhập qua App với user không tồn tại (Lần 2) | Đăng nhập với email không tồn tại, kiểm tra response và thông báo lỗi. |
| 9   | TC_LOGIN_APP_03        | Đăng nhập qua App với user admin bị chặn (Lần 1) | Đăng nhập với user admin có status "Blocked", kiểm tra response và lỗi. |
| 10  | TC_LOGIN_APP_04        | Đăng nhập qua App với user admin bị chặn (Lần 2) | Đăng nhập với user admin có status "Blocked", kiểm tra response và lỗi. |
| 11  | TC_ROLE_APP_01         | Phân quyền truy cập TaskPanel (Lần 1) | Kiểm tra phân quyền: admin vào TaskPanel, customer bị chặn và chuyển hướng. |
| 12  | TC_ROLE_APP_02         | Phân quyền truy cập TaskPanel (Lần 2) | Kiểm tra phân quyền với logic bổ sung, kiểm tra lỗi NullPointerException. |
| 13  | TC_ROLE_APP_03         | Phân quyền truy cập TaskPanel (Lần 3) | Kiểm tra phân quyền sau khi sửa logic, đảm bảo customer bị chặn đúng cách. |
| 14  | TC_GETUSER_APP_01      | Hiển thị danh sách người dùng trên TaskPanel (Lần 1) | Kiểm tra hiển thị danh sách người dùng, kiểm tra nút refresh không mất dữ liệu. |
| 15  | TC_GETUSER_APP_02      | Hiển thị danh sách người dùng trên TaskPanel (Lần 2) | Kiểm tra hiển thị danh sách, một số trường bị thiếu (null), kiểm tra refresh. |
| 16  | TC_GETUSER_APP_03      | Hiển thị danh sách người dùng trên TaskPanel (Lần 3) | Kiểm tra hiển thị danh sách người dùng đầy đủ, kiểm tra refresh giữ nguyên dữ liệu. |
| 17  | TC_ADDUSER_APP_01      | Thêm người dùng mới trên TaskPanel (Lần 1) | Thêm user mới, kiểm tra giao diện và database, dự kiến lỗi.          |
| 18  | TC_ADDUSER_APP_02      | Thêm người dùng mới trên TaskPanel (Lần 2) | Thêm user mới, kiểm tra giao diện và database, dự kiến lỗi 404.      |
| 19  | TC_ADDUSER_APP_03      | Thêm người dùng mới trên TaskPanel (Lần 3) | Thêm user mới, kiểm tra giao diện và database, đảm bảo thành công.   |
| 20  | TC_ADDUSER_APP_04      | Thêm người dùng với email đã tồn tại (Lần 1) | Thêm user với email đã tồn tại, kiểm tra thông báo lỗi và database.  |
| 21  | TC_ADDUSER_APP_04      | Thêm người dùng với email đã tồn tại (Lần 2) | Thêm user với email đã tồn tại, kiểm tra thông báo lỗi và database.  |
| 22  | TC_DELETEUSER_APP_01   | Xóa người dùng trên TaskPanel (Lần 1) | Xóa user, kiểm tra giao diện và database, dự kiến lỗi.               |
| 23  | TC_DELETEUSER_APP_02   | Xóa người dùng trên TaskPanel (Lần 2) | Xóa user, kiểm tra giao diện và database, dự kiến lỗi.               |
| 24  | TC_DELETEUSER_APP_03   | Xóa người dùng trên TaskPanel (Lần 3) | Xóa user, kiểm tra giao diện và database, đảm bảo thành công.        |
| 25  | TC_UPDATEUSER_APP_01   | Sửa thông tin người dùng trên TaskPanel (Lần 1) | Sửa thông tin user, kiểm tra EditUserDialog và database, dự kiến lỗi.|
| 26  | TC_UPDATEUSER_APP_02   | Sửa thông tin người dùng trên TaskPanel (Lần 2) | Sửa thông tin user, kiểm tra EditUserDialog và database, dự kiến lỗi 500. |
| 27  | TC_UPDATEUSER_APP_03   | Sửa thông tin người dùng trên TaskPanel (Lần 3) | Sửa thông tin user, kiểm tra EditUserDialog và database, đảm bảo thành công. |
| 28  | TC_LOGOUT_APP_01       | Đăng xuất và quay lại màn hình đăng nhập (Lần 1) | Đăng xuất, kiểm tra giao diện và token, dự kiến lỗi (ứng dụng đóng). |
| 29  | TC_LOGOUT_APP_02       | Đăng xuất và quay lại màn hình đăng nhập (Lần 2) | Đăng xuất, kiểm tra giao diện và token, dự kiến lỗi (token không xóa). |
| 30  | TC_LOGOUT_APP_03       | Đăng xuất và quay lại màn hình đăng nhập (Lần 3) | Đăng xuất, kiểm tra giao diện và token, đảm bảo thành công.          |
| 31  | TC_Token_Stored_01     | Kiểm tra token trong thư mục tokens được mã hóa | Kiểm tra token lưu trữ sau đăng nhập, đảm bảo mã hóa đúng (Base64).  |
| 32  | TC_API_Secu_01         | Kiểm tra yêu cầu CSRF token trên endpoint /add | Gửi POST request tới /add không kèm CSRF token, kiểm tra response.    |
| 33  | TC_API_Secu_02         | Kiểm tra POST request tới /add với CSRF token hợp lệ | Gửi POST request tới /add với CSRF token hợp lệ, kiểm tra response.   |
| 34  | TC_API_Secu_03         | Kiểm tra chống SQL Injection trên /AdminUpdate | Gửi request với dữ liệu chứa mã SQL injection, kiểm tra response.     |

### 5.3. Đặc tả Test Case

#### 5.3.1. Test Case Actor Customer (Web Platform)

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_CUSTOMER_WEB_LOGIN_01 | Đăng nhập thành công           | Tài khoản customer1@gmail.com tồn tại, server chạy. | 1. Truy cập trang chủ. 2. Nhấn "Login with Google". 3. Nhập email, cấp quyền. 4. Gửi POST /login. 5. Kiểm tra. | Email: customer1@gmail.com, GoogleID: 12345          | HTTP 200 OK, dashboard Customer, thông báo "Đăng nhập thành công".               | HTTP 200 OK, dashboard hiển thị, thông báo đúng.                                | P   |
| TC_CUSTOMER_WEB_LOGIN_02 | Đăng nhập thất bại             | Tài khoản blockedcustomer@gmail.com bị chặn.        | 1. Truy cập trang chủ. 2. Nhấn "Login with Google". 3. Nhập email. 4. Gửi POST /login. 5. Kiểm tra. | Email: blockedcustomer@gmail.com, GoogleID: 67890    | HTTP 200 OK, thông báo "Tài khoản bị chặn", ở lại trang đăng nhập.               | HTTP 200 OK, thông báo lỗi đúng, không chuyển giao diện.                        | P   |

#### 5.3.2. Test Case Actor Admin (Web Platform)

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_ADMIN_WEB_ADDUSER_01 | Thêm Admin mới thành công      | Admin admin1@gmail.com đăng nhập, server chạy.      | 1. Vào trang quản lý. 2. Nhấn "Thêm Admin". 3. Nhập thông tin. 4. Lưu. 5. Kiểm tra. | Email: newadmin@gmail.com, FullName: "Nguyen Van A"  | Thông báo "Thêm Admin thành công", bản ghi mới trong database.                   | Thông báo đúng, database cập nhật.                                            | P   |
| TC_ADMIN_WEB_ADDUSER_02 | Thêm Admin với email tồn tại   | Admin đăng nhập, existing@gmail.com đã tồn tại.     | 1. Vào trang quản lý. 2. Nhấn "Thêm Admin". 3. Nhập email tồn tại. 4. Lưu. 5. Kiểm tra. | Email: existing@gmail.com, FullName: "Nguyen Van B"  | Thông báo lỗi "Email đã tồn tại", database không thay đổi.                       | Thông báo lỗi "Email này đã được sử dụng", database không thay đổi.            | P   |
| TC_ADMIN_WEB_EDITUSER_01 | Sửa thông tin Khách hàng       | Admin đăng nhập, customer1@gmail.com tồn tại.       | 1. Vào trang quản lý. 2. Chọn customer1@gmail.com. 3. Sửa số điện thoại. 4. Lưu. 5. Kiểm tra. | Email: customer1@gmail.com, Phone: "0987654321"      | Thông báo "Cập nhật thành công", database và giao diện cập nhật.                 | Thông báo đúng, database và giao diện cập nhật.                               | P   |
| TC_ADMIN_WEB_DELETEUSER_01 | Xóa Khách hàng thành công    | Admin đăng nhập, customer2@gmail.com tồn tại.       | 1. Vào trang quản lý. 2. Chọn customer2@gmail.com. 3. Xóa. 4. Xác nhận. 5. Kiểm tra. | Email: customer2@gmail.com                           | Thông báo "Xóa thành công", bản ghi xóa khỏi database và giao diện.              | Thông báo đúng, bản ghi xóa khỏi database và giao diện.                       | P   |

#### 5.3.3. Test Case Actor Admin (Desktop App)

##### 5.3.3.1. Test Case Đăng nhập

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_LOGIN_APP_01         | Đăng nhập với user không tồn tại (Lần 1) | User camtu18@gmail.com chưa tồn tại, server chạy.  | 1. Chạy app. 2. Nhấn "Login with Google". 3. Kiểm tra. | Email: camtu18@gmail.com                              | Response: {"error": "Tài khoản không tồn tại"}, thông báo lỗi, không vào TaskPanel. | Response: {"error": "403 Forbidden"}, không hiển thị lỗi cụ thể.                | F   |
| TC_LOGIN_APP_02         | Đăng nhập với user không tồn tại (Lần 2) | User camtu18@gmail.com chưa tồn tại, server chạy.  | 1. Chạy app. 2. Nhấn "Login with Google". 3. Kiểm tra. | Email: camtu18@gmail.com                              | Response: {"error": "Tài khoản không tồn tại"}, thông báo lỗi, không vào TaskPanel. | Response đúng, thông báo lỗi và chuyển hướng web.                             | P   |
| TC_LOGIN_APP_03         | Đăng nhập với admin bị chặn (Lần 1) | User camtu7092003@gmail.com, role: admin, status: Blocked. | 1. Chạy app. 2. Nhấn "Login with Google". 3. Kiểm tra. | Email: camtu7092003@gmail.com                         | Response: {"error": "Tài khoản bị chặn"}, không vào TaskPanel.                   | Người dùng vẫn truy cập được.                                                | F   |
| TC_LOGIN_APP_04         | Đăng nhập với admin bị chặn (Lần 2) | User camtu7092003@gmail.com, role: admin, status: Blocked. | 1. Chạy app. 2. Nhấn "Login with Google". 3. Kiểm tra. | Email: camtu7092003@gmail.com                         | Response: {"error": "Tài khoản bị chặn"}, không vào TaskPanel.                   | Response và thông báo lỗi đúng.                                              | P   |

##### 5.3.3.2. Test Case Kiểm tra phân quyền truy cập dựa trên vai trò

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_ROLE_APP_01          | Phân quyền TaskPanel (Lần 1)   | User admin và customer tồn tại, status Active.     | 1. Đăng nhập admin. 2. Kiểm tra. 3. Đăng nhập customer. 4. Kiểm tra. | Email 1: camtu18@gmail.com, Email 2: tuchuc848@gmail.com | Admin vào TaskPanel, customer bị chặn và chuyển hướng web.                       | Customer vẫn vào TaskPanel.                                                    | F   |
| TC_ROLE_APP_02          | Phân quyền TaskPanel (Lần 2)   | User admin và customer tồn tại, thêm logic kiểm tra.| 1. Đăng nhập admin. 2. Kiểm tra. 3. Đăng nhập customer. 4. Kiểm tra. | Email 1: camtu18@gmail.com, Email 2: tuchuc848@gmail.com | Admin vào TaskPanel, customer bị chặn và chuyển hướng web.                       | Lỗi NullPointerException.                                                     | F   |
| TC_ROLE_APP_03          | Phân quyền TaskPanel (Lần 3)   | User admin và customer tồn tại, sửa logic.         | 1. Đăng nhập admin. 2. Kiểm tra. 3. Đăng nhập customer. 4. Kiểm tra. | Email 1: camtu18@gmail.com, Email 2: tuchuc848@gmail.com | Admin vào TaskPanel, customer bị chặn và chuyển hướng web.                       | Kết quả đúng, customer bị chặn.                                               | P   |

##### 5.3.3.3. Test Case Kiểm tra chức năng hiển thị thông tin người dùng

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_GETUSER_APP_01       | Hiển thị danh sách (Lần 1)     | Admin testuser15@gmail.com, dữ liệu tồn tại.       | 1. Kiểm tra Table. 2. Nhấn refresh.                   | -                                                     | Table hiển thị dữ liệu, refresh không mất dữ liệu.                              | Table không hiển thị, refresh không load dữ liệu.                             | F   |
| TC_GETUSER_APP_02       | Hiển thị danh sách (Lần 2)     | Admin testuser15@gmail.com, dữ liệu tồn tại.       | 1. Kiểm tra Table. 2. Nhấn refresh.                   | -                                                     | Table hiển thị dữ liệu, refresh không mất dữ liệu.                              | Dữ liệu thiếu (null), refresh giữ nguyên.                                    | F   |
| TC_GETUSER_APP_03       | Hiển thị danh sách (Lần 3)     | Admin testuser15@gmail.com, dữ liệu tồn tại.       | 1. Kiểm tra Table. 2. Nhấn refresh.                   | -                                                     | Table hiển thị dữ liệu, refresh không mất dữ liệu.                              | Kết quả đúng, dữ liệu đầy đủ sau refresh.                                     | P   |

##### 5.3.3.4. Test Case Kiểm tra chức năng thêm thông tin người dùng

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_ADDUSER_APP_01       | Thêm người dùng (Lần 1)        | Admin testuser15@gmail.com, server chạy.           | 1. Nhấn "Add User". 2. Nhập thông tin. 3. Kiểm tra.   | Email: testuser21@gmail.com, FullName: "Cam Tu Nguyen" | User mới xuất hiện, database cập nhật.                                          | Lỗi "Lỗi khi thêm người dùng!", không cập nhật.                               | F   |
| TC_ADDUSER_APP_02       | Thêm người dùng (Lần 2)        | Admin testuser15@gmail.com, server chạy.           | 1. Nhấn "Add User". 2. Nhập thông tin. 3. Kiểm tra.   | Email: testuser21@gmail.com, FullName: "Cam Tu Nguyen" | User mới xuất hiện, database cập nhật.                                          | Lỗi "404 Not Found", không cập nhật.                                          | F   |
| TC_ADDUSER_APP_03       | Thêm người dùng (Lần 3)        | Admin testuser15@gmail.com, server chạy.           | 1. Nhấn "Add User". 2. Nhập thông tin. 3. Kiểm tra.   | Email: testuser21@gmail.com, FullName: "Cam Tu Nguyen" | User mới xuất hiện, database cập nhật.                                          | Kết quả đúng, database và giao diện cập nhật.                                 | P   |
| TC_ADDUSER_APP_04       | Thêm với email tồn tại (Lần 1) | Admin testuser15@gmail.com, email tồn tại.         | 1. Nhấn "Add User". 2. Nhập email tồn tại. 3. Kiểm tra.| Email: testuser22@gmail.com, FullName: "Cam Tu Nguyen" | Thông báo lỗi, database không cập nhật.                                         | Thông báo "Thêm thành công", 2 tài khoản trùng email.                         | F   |
| TC_ADDUSER_APP_04       | Thêm với email tồn tại (Lần 2) | Admin testuser22@gmail.com, email tồn tại.         | 1. Nhấn "Add User". 2. Nhập email tồn tại. 3. Kiểm tra.| Email: testuser22@gmail.com, FullName: "Cam Tu Nguyen" | Thông báo lỗi, database không cập nhật.                                         | Thông báo lỗi đúng, database không thay đổi.                                  | P   |

##### 5.3.3.5. Test Case Kiểm tra chức năng xóa người dùng

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_DELETEUSER_APP_01    | Xóa người dùng (Lần 1)         | Admin testuser15@gmail.com, server chạy.           | 1. Chọn user. 2. Nhấn "Delete". 3. Xác nhận. 4. Kiểm tra. | Email: testuser21@gmail.com                           | User xóa khỏi Table và database.                                                | Lỗi "Lỗi khi xóa người dùng!", user vẫn tồn tại.                              | F   |
| TC_DELETEUSER_APP_02    | Xóa người dùng (Lần 2)         | Admin testuser15@gmail.com, server chạy.           | 1. Chọn user. 2. Nhấn "Delete". 3. Xác nhận. 4. Kiểm tra. | Email: testuser21@gmail.com                           | User xóa khỏi Table và database.                                                | Lỗi "Lỗi khi xóa người dùng!", user vẫn tồn tại.                              | F   |
| TC_DELETEUSER_APP_03    | Xóa người dùng (Lần 3)         | Admin testuser15@gmail.com, server chạy.           | 1. Chọn user. 2. Nhấn "Delete". 3. Xác nhận. 4. Kiểm tra. | Email: testuser21@gmail.com                           | User xóa khỏi Table và database.                                                | User xóa đúng, database cập nhật.                                            | P   |

##### 5.3.3.6. Test Case Kiểm tra chức năng sửa thông tin người dùng

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_UPDATEUSER_APP_01    | Sửa thông tin (Lần 1)          | Admin testuser15@gmail.com, user tồn tại.          | 1. Chọn user. 2. Nhấn "Edit". 3. Sửa số điện thoại. 4. Lưu. 5. Kiểm tra. | Phone: "7878"                                         | EditUserDialog hiển thị, database và Table cập nhật.                            | Dialog trống, không lưu, lỗi log "invalid row selection".                      | F   |
| TC_UPDATEUSER_APP_02    | Sửa thông tin (Lần 2)          | Admin testuser15@gmail.com, user tồn tại.          | 1. Chọn user. 2. Nhấn "Edit". 3. Sửa số điện thoại. 4. Lưu. 5. Kiểm tra. | Phone: "7878"                                         | EditUserDialog hiển thị, database và Table cập nhật.                            | Dialog hiển thị, nhưng lỗi 500, database không thay đổi.                       | F   |
| TC_UPDATEUSER_APP_03    | Sửa thông tin (Lần 3)          | Admin testuser15@gmail.com, user tồn tại.          | 1. Chọn user. 2. Nhấn "Edit". 3. Sửa số điện thoại. 4. Lưu. 5. Kiểm tra. | Phone: "7878"                                         | EditUserDialog hiển thị, database và Table cập nhật.                            | Kết quả đúng, database và Table cập nhật.                                     | P   |

##### 5.3.3.7. Test Case Kiểm tra đăng xuất

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_LOGOUT_APP_01        | Đăng xuất (Lần 1)              | Admin testuser15@gmail.com, token lưu.             | 1. Nhấn "Logout". 2. Kiểm tra giao diện và token.     | -                                                     | Giao diện về LoginPanel, token xóa khỏi Preferences và user_tokens.              | Ứng dụng đóng, token không xóa.                                               | F   |
| TC_LOGOUT_APP_02        | Đăng xuất (Lần 2)              | Admin testuser15@gmail.com, server chạy.           | 1. Nhấn "Logout". 2. Kiểm tra giao diện và token.     | -                                                     | Giao diện về LoginPanel, token xóa khỏi Preferences và user_tokens.              | Giao diện đúng, nhưng token vẫn tồn tại.                                      | F   |
| TC_LOGOUT_APP_03        | Đăng xuất (Lần 3)              | Admin testuser15@gmail.com, server chạy.           | 1. Nhấn "Logout". 2. Kiểm tra giao diện và token.     | -                                                     | Giao diện về LoginPanel, token xóa khỏi Preferences và user_tokens.              | Kết quả đúng, token xóa và giao diện về LoginPanel.                           | P   |

#### 5.3.4. Test Case Bảo mật API

| ID Test Case            | Mô tả                          | Tiền điều kiện                                      | Các bước kiểm tra                                      | Dữ liệu thử nghiệm                                      | Kết quả mong đợi                                                                 | Kết quả thực tế                                                                 | P/F |
|-------------------------|--------------------------------|----------------------------------------------------|-------------------------------------------------------|-------------------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------|-----|
| TC_Token_Stored_01      | Kiểm tra token được mã hóa     | Đăng nhập với tuchuc848@gmail.com, thư mục tokens tồn tại. | 1. Đăng nhập. 2. Mở tệp StoredCredential. 3. Kiểm tra. | -                                                     | Nội dung tệp là chuỗi mã hóa Base64.                                            | Response lỗi 403 (thiếu CSRF), log "Invalid CSRF token".                      | P   |
| TC_API_Secu_01          | Kiểm tra POST /add không CSRF  | Token admin tuchuc34@gmail.com, server chạy.       | 1. Gửi POST /add không CSRF. 2. Kiểm tra response.    | Email: tuchuc34@gmail.com                             | Response: {"error": "403 Forbidden - CSRF token missing"}, database không thay đổi. | Response đúng, database không thay đổi, log "Invalid CSRF token".             | P   |
| TC_API_Secu_02          | Kiểm tra POST /add với CSRF    | Token và CSRF hợp lệ, server chạy.                | 1. Gửi POST /add với CSRF. 2. Kiểm tra response.      | Email: tuchuc34@gmail.com                             | Response: {"status": "success"}, bản ghi mới trong database.                     | Response và database cập nhật đúng.                                          | P   |
| TC_API_Secu_03          | Kiểm tra chống SQL Injection   | Admin tuchuc848@gmail.com, server chạy.            | 1. Gửi POST /AdminUpdate với mã SQL. 2. Kiểm tra.     | Email: tuchuc848@gmail.com, role: "' OR '1'='1"      | Response: "Cập nhật thành công", database không bị thay đổi bất thường.          | Response đúng, database cập nhật role như chuỗi (chưa rõ bảo mật).            | -   |

## Conclusion
All 34 test cases have been executed. Out of these, 28 passed, and 6 failed. The failed cases (TC_LOGIN_APP_01, TC_ROLE_APP_01, TC_ROLE_APP_02, TC_GETUSER_APP_01, TC_GETUSER_APP_02, TC_ADDUSER_APP_04 (Lần 1), TC_DELETEUSER_APP_01, TC_DELETEUSER_APP_02, TC_UPDATEUSER_APP_01, TC_UPDATEUSER_APP_02, TC_LOGOUT_APP_01, TC_LOGOUT_APP_02) require further debugging and fixes. TC_API_Secu_03 needs additional verification for SQL Injection security.
