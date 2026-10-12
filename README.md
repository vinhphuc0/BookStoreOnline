## 1. Mở đúng bản mới

1. Giải nén ZIP mới ra một thư mục riêng
2. Mở `BookStoreOnline.sln` trong thư mục mới bằng Visual Studio 2022.
4. Nếu được hỏi tin cậy, kiểm tra đúng thư mục mới rồi chọn Trust and Continue.


## 2. Kiểm tra .NET 8 SDK

Cần có ít nhất một dòng bắt đầu bằng `8.0.`. Nếu chưa có, tải **.NET 8 SDK Windows x64** tại https://dotnet.microsoft.com/en-us/download/dotnet/8.0 . Chọn SDK, không chỉ chọn Runtime. Sau khi cài hãy đóng rồi mở lại Visual Studio.

Nếu dùng Visual Studio Installer: chọn Visual Studio 2022 → Modify → Workloads → ASP.NET and web development. Kiểm tra Individual components có .NET 8 SDK và SQL Server Express LocalDB nếu bạn dùng LocalDB.


## 3. Build trước

Chọn **Build → Rebuild Solution** (hoặc Ctrl+Shift+B để Build). Nếu báo thiếu SDK, làm bước 2. Nếu NuGet chưa tải xong, nhấp phải Solution → Restore NuGet Packages, rồi Build lại.


## 4. Tạo database

1.Mở Start của Windows → tìm Visual Studio Installer.
2.Tại Visual Studio Community 2022, nhấn Modify.
3.Chọn tab Individual components.
4.Trong ô tìm kiếm, nhập LocalDB.
5.Tích SQL Server Express … LocalDB.
6.Nhấn Modify ở góc dưới để cài. Microsoft hỗ trợ cài LocalDB bằng cách này
7. Về bước 4, nhập SQL Server Data Tools
8.Tích mục SQL Server Data Tools → nhấn Modify để cài. 
9.Mở lại dự án → View → SQL Server Object Explorer.

10.Trong Solution Explorer bên phải, nhấn mũi tên cạnh BookStoreOnline để mở các thư mục.
11.Mở thư mục Database → nhấp đúp 01_schema.sql,2,3,4,5...
12.Ở bảng bên trái, nhấp phải dòng (localdb)\MSSQLLocalDB → chọn New Query.
13.Sao chép database 01-06 Dán nội dung vào New Query vừa tạo.
Nhấn nút Execute ở thanh công cụ của cửa sổ SQL
 
 
## 6. Chạy website



## 7. Tạo tài khoản quản trị

Đăng ký tài khoản trên website bằng email của bạn. Sau đó trong SSMS chạy, thay email mẫu bằng email vừa đăng ký:

```sql
USE BookStoreOnline;
UPDATE Users SET Role=N'Admin' WHERE Email=N'email-cua-ban@example.com';
```

Đăng xuất rồi đăng nhập lại; menu Quản trị xuất hiện. Không có mật khẩu admin mặc định.


