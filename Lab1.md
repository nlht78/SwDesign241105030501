# 1. Phân tích kiến trúc
## Kiến trúc đề xuất
Kiến trúc phù hợp cho hệ thống quản lý Payroll (bảng lương) nên dựa trên kiến trúc ba lớp (Three-tier architecture) bao gồm:

- Lớp Giao Diện (Presentation Layer): Lớp này chứa các thành phần liên quan đến giao diện người dùng, như các màn hình đăng nhập, chọn phương thức thanh toán, xem và tạo báo cáo. Lớp này cung cấp phương thức tương tác cho người dùng hệ thống, ví dụ như nhân viên, quản trị viên bảng lương.
- Lớp Xử Lý Logic (Business Logic Layer): Lớp này chứa tất cả các quy tắc kinh doanh liên quan đến bảng lương. Nó sẽ bao gồm các thành phần cho các quy trình tính toán bảng lương, duy trì thông tin thời gian làm việc (timecard), xử lý đơn đặt hàng mua hàng của nhân viên hưởng hoa hồng, và chọn phương thức thanh toán. Lớp này cũng chịu trách nhiệm xử lý các yêu cầu từ người dùng.
- Lớp Dữ Liệu (Data Layer): Lớp này lưu trữ dữ liệu liên quan đến hệ thống, như thông tin về nhân viên, thời gian làm việc, phương thức thanh toán, đơn đặt hàng, và bảng lương. Lớp này cũng chịu trách nhiệm giao tiếp với các cơ sở dữ liệu bên ngoài như ngân hàng (khi thực hiện việc chuyển khoản).

## Giải thích lý do lựa chọn kiến trúc
- Tách biệt các lớp xử lý: Ba lớp trên tách biệt rõ ràng giữa giao diện người dùng, logic xử lý nghiệp vụ, và lưu trữ dữ liệu. Điều này giúp hệ thống dễ dàng bảo trì, nâng cấp, và mở rộng trong tương lai.
- Tính linh hoạt: Kiến trúc này dễ dàng tích hợp với các hệ thống bên ngoài, như hệ thống ngân hàng để thực hiện chuyển khoản tự động.
- Bảo mật: Việc phân tách này cũng giúp bảo mật dữ liệu, đảm bảo rằng lớp giao diện không thể trực tiếp truy cập cơ sở dữ liệu mà phải thông qua lớp xử lý nghiệp vụ.
## Biểu đồ Package mô tả kiến trúc:
![Package Diagram](https://www.planttext.com/api/plantuml/png/T99HJW8n48RVUufvKn-u0I44qCG4b80N6BeZD7JRJMU8sHXFveD7yWgsYri1ozjqPZhpzV_x_VarPi4WXzegtXi7mJCf9KOimHBr7hV4C8XX6xori6vPg8QPmMt0Mgdcs0BBG4nEK8ntSsmfm73uu6r5OJI2TmMWBJB3t6-DowSrMT8IHzVnwe9avwjScmP2eHKrFaXEBj347SQzc9eqXafz_15C3cmSCQSLkaTuyXMT0Vo-OufM7sn7cqltTMDzIxH05-Sbf5nw3l4XXNpFSL8w8PgXO0-IuWtoEKoVp8a9klrHuKSd51Nk0EF86rZH4PTtfc7OaBmHER1fFAl_wWy6eu8YgY1IwioaQTEw8MrUZGRjdOl-fALmwviKeBrJ1TUw8GLfJqtiUWeQNthQzHM4lV0WStS25eMxHgN6vAhquNy0003__mC0) 
