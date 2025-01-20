# 📝 Minimal API với ASP.NET Core và In-Memory Database

## 🛠 Tổng quan

Dự án này giới thiệu cách tạo một **Minimal API** với **ASP.NET Core**, tập trung vào việc giảm thiểu phụ thuộc và cấu hình. API sử dụng cơ sở dữ liệu **In-Memory** để thực hiện các chức năng CRUD (Create, Read, Update, Delete) với danh sách công việc cần làm (To-Do List). Dự án là lựa chọn lý tưởng cho các microservices hoặc ứng dụng yêu cầu cấu hình nhẹ và tốc độ cao.

---

## 📂 Cấu trúc dự án

- **`Program.cs`**:
  - Chứa toàn bộ logic xử lý chính của ứng dụng.
  - Định nghĩa các điểm cuối (endpoints) để thực hiện các chức năng CRUD.
  - Cấu hình cơ sở dữ liệu **In-Memory** và tích hợp các dịch vụ cần thiết.

- **Models**:
  - `Todo.cs`: Định nghĩa cấu trúc dữ liệu của một công việc với các thuộc tính:
    - `Id`: Định danh duy nhất cho công việc.
    - `Name`: Tên công việc.
    - `IsComplete`: Trạng thái hoàn thành của công việc.

  - `TodoDb.cs`: Cấu hình lớp database context, sử dụng `EntityFrameworkCore` để quản lý dữ liệu.

- **Endpoints**:
  - Định nghĩa trực tiếp trong `Program.cs`, mỗi endpoint tương ứng với một chức năng của API:
    - `GET`, `POST`, `PUT`, và `DELETE`.

---

## 🌟 Chức năng chính

| **Chức năng**                      | **HTTP Method** | **Endpoint**            | **Mô tả**                                                                 |
|------------------------------------|-----------------|-------------------------|---------------------------------------------------------------------------|
| **Lấy danh sách công việc**         | GET             | `/todoitems`            | Lấy toàn bộ danh sách công việc hiện có trong cơ sở dữ liệu.             |
| **Lấy danh sách công việc hoàn thành** | GET             | `/todoitems/complete`   | Lấy danh sách các công việc đã được đánh dấu hoàn thành.                 |
| **Lấy thông tin chi tiết**          | GET             | `/todoitems/{id}`       | Lấy thông tin chi tiết của một công việc dựa trên ID.                   |
| **Thêm công việc mới**              | POST            | `/todoitems`            | Thêm một công việc mới vào danh sách.                                    |
| **Cập nhật thông tin công việc**    | PUT             | `/todoitems/{id}`       | Cập nhật thông tin của một công việc đã tồn tại, xác định bằng ID.       |
| **Xóa công việc**                   | DELETE          | `/todoitems/{id}`       | Xóa một công việc khỏi danh sách dựa trên ID.                            |

---

## 🌟 Kết quả đạt được

1. **Triển khai thành công Minimal API**:
   - API được xây dựng với cấu trúc đơn giản, sử dụng ít phụ thuộc nhất có thể.

2. **Sử dụng cơ sở dữ liệu In-Memory**:
   - Tích hợp cơ sở dữ liệu nhẹ để lưu trữ dữ liệu tạm thời, không yêu cầu cài đặt phức tạp.

3. **Tích hợp Entity Framework Core**:
   - Hỗ trợ truy vấn và thao tác dữ liệu nhanh chóng thông qua các phương thức của `DbContext`.

4. **Hỗ trợ Swagger UI**:
   - Tài liệu hóa API tự động, cho phép kiểm tra các endpoint dễ dàng thông qua giao diện trực quan.

5. **Tối ưu cho học tập và thử nghiệm**:
   - Phù hợp với các dự án thử nghiệm hoặc minh họa cách làm việc của Minimal API.

---

## 🔗 Tham khảo

- [Microsoft Documentation: Minimal Web API](https://learn.microsoft.com/en-us/aspnet/core/tutorials/min-web-api?view=aspnetcore-9.0&tabs=visual-studio)
- [Entity Framework Core In-Memory Provider](https://learn.microsoft.com/en-us/ef/core/providers/in-memory/)

