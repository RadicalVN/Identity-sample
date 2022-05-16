# Identity-sample
TÍCH HỢP IDENTITY FRAMEWORK VÀO SOLUTION WEB MVC

1. Trong Program.cs (hoặc Startup.cs)
- Thêm (đăng ký) các services vào container
  + AddDbContext
  + AddDatabaseDeveloperPageExceptionFilter
  + AddDefaultIdentity
- Thêm cài đặt chọn môi trường
  if (app.Environment.IsDevelopment())
  {
      app.UseMigrationsEndPoint();
  }
- Thêm Authentication
  app.UseAuthentication();
  
- Thêm MapRazorPages
  app.MapRazorPages();

2. Trong appsetting.json
- Lưu thông tin chuỗi kết nối database (ConnectionStrings)

3. Tạo Folder Data
  => Trong này tạo class AppDbContext kế thừa từ IdentityDbContext
  
4. Add thêm các package :
          Microsoft.AspNetCore.Diagnostics.EntityFrameworkCore
          Microsoft.AspNetCore.Identity.EntityFrameworkCore
          Microsoft.AspNetCore.Identity.UI
          Microsoft.EntityFrameworkCore.SqlServer
          Microsoft.EntityFrameworkCore.Tools
          
5. Tạo Areas (Areas) 
=> Trong Areas tạo Folder (Identity) 
=> Trong Identity tạo Folder (Pages) để chứa các Razor Pages 
=> Trong Pages tạo Razor Page tên _ViewStart.cshtml 
=>  Nội dung trong _ViewStart.cshtml:
@{
    // Chỉ định Layout.
    Layout = "/Views/Shared/_Layout.cshtml";
}

6. Thêm partial _LoginPartial.cshtml vào _layout.cshtml
  <partial name="_LoginPartial" />
  
7. Tạo trang đăng ký/đăng nhập _loginpartial.cshtml\
  Trong này tiến hành Route
  Route trong View bằng cách tạo các liên kết dựa vào asp-area
