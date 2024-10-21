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

# 2. Cơ chế phân tích
## Các cơ chế phân tích cần giải quyết: 
- Quản lý thông tin nhân viên: Cần cơ chế để thêm, sửa, xóa thông tin nhân viên, và đảm bảo tính toàn vẹn dữ liệu nhân viên khi xóa nhân viên (như xóa các thông tin liên quan đến hợp đồng hoặc báo cáo cũ).
- Tính toán bảng lương: Cơ chế này chịu trách nhiệm tính toán lương dựa trên thời gian làm việc và các khoản hoa hồng, trợ cấp, khấu trừ thuế.
- Quản lý thời gian làm việc (Timecard Management): Hệ thống cần cơ chế để nhân viên nhập thời gian làm việc và các số liệu liên quan, đồng thời hỗ trợ việc nộp và khóa timecard khi hết thời gian sửa đổi.
- Xử lý đơn đặt hàng (Order Management): Cơ chế này dành cho nhân viên hưởng hoa hồng để nhập và cập nhật các đơn đặt hàng liên quan đến sản phẩm/dịch vụ họ bán.
- Lựa chọn phương thức thanh toán: Cơ chế này giúp nhân viên lựa chọn cách nhận lương: nhận trực tiếp hoặc qua tài khoản ngân hàng.
- Tạo báo cáo: Cần cơ chế tạo báo cáo cho quản trị viên và nhân viên, bao gồm thông tin về số giờ làm việc, thời gian nghỉ phép, và tổng số tiền nhận được trong năm.

# 3. Phân tích ca sử dụng Payment
## Các lớp phân tích
- Employee: Đại diện cho nhân viên sử dụng hệ thống.
- PaymentMethodSelector: Lớp chịu trách nhiệm hiển thị và quản lý việc chọn phương thức thanh toán.
- BankSystem: Lớp giao tiếp với hệ thống ngân hàng khi chọn phương thức thanh toán qua chuyển khoản.
- PaymentDatabase: Lớp quản lý việc lưu trữ thông tin liên quan đến phương thức thanh toán của nhân viên.
## Sequence Diagram 
- Employee tương tác với PaymentMethodSelector để chọn phương thức thanh toán.
- PaymentMethodSelector xác thực thông tin, nếu chọn chuyển khoản, nó sẽ gửi yêu cầu đến BankSystem để xác nhận tài khoản.
- Sau khi xác nhận, PaymentMethodSelector cập nhật thông tin vào PaymentDatabase.
## Một số thuộc tính và quan hệ giữa các lớp:
- Employee có thuộc tính paymentMethod.
- PaymentMethodSelector chứa phương thức selectPaymentMethod() để quản lý quá trình chọn.
- BankSystem có phương thức verifyBankAccount() để xác nhận thông tin ngân hàng.

# 4. Phân tích ca sử dụng Maintain Timecard
## Các lớp phân tích
Employee: Đại diện cho nhân viên sử dụng hệ thống.
Timecard: Lớp lưu trữ thông tin về thời gian làm việc.
TimecardManager: Lớp chịu trách nhiệm quản lý việc nhập và nộp timecard.
ProjectManagementSystem: Lớp quản lý danh sách các mã số dự án để tính toán thời gian làm việc theo dự án.
## Sequence Diagram 
Employee yêu cầu TimecardManager để cập nhật timecard.
TimecardManager lấy danh sách mã số dự án từ ProjectManagementSystem.
Sau khi Employee nhập thông tin, TimecardManager xác nhận và lưu vào Timecard.
## Một số thuộc tính và quan hệ giữa các lớp:
Employee có thuộc tính currentTimecard.
TimecardManager chứa phương thức updateTimecard() để quản lý việc nhập thông tin.
Timecard có các thuộc tính như hoursWorked, projectChargeNumber.

# 5. Hợp nhất kết quả phân tích
Hai ca sử dụng "Select Payment Method" và "Maintain Timecard" đều có chung những yêu cầu cơ bản về bảo mật (nhân viên phải đăng nhập trước khi sử dụng hệ thống), quản lý thông tin người dùng (Employee), và sự tích hợp với các hệ thống bên ngoài (hệ thống ngân hàng và hệ thống quản lý dự án).

## Các lớp chung
- Employee: Được dùng cho cả hai ca sử dụng.
- Database: Được dùng để lưu trữ cả thông tin phương thức thanh toán và thông tin timecard.

