# Bài tập Trainee Colombo 2018
Thực hiện bởi [Nguyễn Phi Huy](https://github.com/huynhan147)
## Base composer package
### 1.Tạo cấu trúc Project : 
`composer create-project buonzz/composer-library-template mylibrary`
- **mylibrary** : Tên thư viện của bạn 
  - Thư mục `src` : Chứa code của bạn
  - Thư mục `test` : chứa code kiểm tra code trong thư mục src
  - `.gitignore` file định nghĩa các file ko cần đưa lên git
  - `LICENSE` Điều khoản và mức độ sử dụng mà các lập trình viên khác dc phép sử dụng
  - `README.md` Tài liệu nhỏ về thư viện ví dụ cách cài đăt , sử dụng ...
  - `composer.json`: Là nơi lưu thông tin về thư viện ví dụ : tên package, tên tác giả , mô tả
  - `phpunit.xml` : Tệp cấu hình của PHPUnit
### 2. Tùy chỉnh các tệp được tạo : 
- Trong `src / YourClass.php` cần đổi tên file theo đúng tên thư viện thực tế. Tên lớp trong `YourClass.php` cần phải khớp với tên file.
- Namespace : Thường thì đặt theo tên user Github của bạn . Tạo theo cú pháp `namespace VendorName \ PackageName;`
- Chỉnh sửa file `composer.json` : `"name": "vendorname/packagename"` sau đó `"psr-4": { "VendorName\\PackageName\\": "src/" }`. Bạn có thể chỉnh sửa thêm tên tác giả, mô tả về package, email,... .
- Sau đó kiểm tra file `composer.json` để đảm bảo ko mắc lỗi bằng lệnh : `composer validate` 
- Tùy chỉnh file README.md nói về một số thông tin về package
### 3. Viết test : 
- Nếu bạn có một `src / Utils.php` , bạn cũng cần phải có `test/ UtilsTest.php`;
- Cài đặt thư viện PHPUnit : `composer install` - Sẽ cài đặt trong `vendor/bin/phpunit`
- Sửa lại namspace thành namspace riêng của bạn
- Chạy PHPUnit bằng : `vendor/bin/phpunit`
### 4. Xuất bản sản phẩm của bạn : 
- Tạo 1 repo trên github và trùng tên vs tên thư viện của bạn
- Vào **Setting** của repo chọn **Webhooks & Services** trên tab **Services** Nhấp vào **Add Service** và chọn **Packagist**
- Bạn cần phải nhập username của bạn trên packagist cùng với token. Để lấy được token , truy cập vào trang profile của bạn và click vào **Show Token** để sao chép và pate vào github. 
- Truy cập  https://packagist.org/packages/submit và dán url repo github của bạn. Đợi một lúc, thư viện của bạn đã có sẵn trên packagist
- Để sử dụng thư viện : 
```
composer init
composer require yourusername/yourpackagename
```
- Sau đó tạo file index.php sẽ tải trình tải tự động
`require 'vendor/autoload.php';`
*Thư viện của bạn đã sẵn sàng sử dụng !!!*
