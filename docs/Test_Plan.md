# Kế hoạch Kiểm thử - SecureInsure

## 1. Giới thiệu
Kế hoạch Kiểm thử này phác thảo cách tiếp cận để kiểm thử hệ thống SecureInsure, tập trung vào chức năng và bảo mật API.

## 2. Mục tiêu
- Đảm bảo chức năng Web và App (đăng nhập, xem thông tin, quản lý người dùng, đăng xuất).
- Xác minh bảo mật API chống lại CSRF và SQL Injection.

## 3. Phạm vi
- **Trong phạm vi**: Kiểm thử chức năng (Web, App) và kiểm thử bảo mật (API).
- **Ngoài phạm vi**: Kiểm thử hiệu năng, khả năng phản hồi trên thiết bị di động.

## 4. Phương pháp Kiểm thử
- **Loại**: Kiểm thử thủ công.
- **Công cụ**: Postman, OWASP ZAP.
- **Môi trường**: Localhost (XAMPP, MySQL), Windows 11.

## 5. Trường hợp Kiểm thử
- Tổng cộng: 34 trường hợp kiểm thử (6 Web, 24 App, 4 API).
- Tiêu chí: Đạt nếu kết quả thực tế khớp với kết quả mong đợi.

## 6. Nguồn lực
- Người kiểm thử: Cẩm Tú.
- Thời gian: 2 tuần, tháng 5 năm 2025.

## 7. Kết quả kiểm thử
- Trường hợp kiểm thử: [App_Testing.md](Test_Cases/App_Testing.md), [Web_Testing.md](Test_Cases/Web_Testing.md), [API_Testing.md](Test_Cases/API_Testing.md)
- Ảnh chụp màn hình: [OWASP ZAP](Screenshots/OWASP_Screenshots), [Postman](Screenshots/Postman_Screenshots)
