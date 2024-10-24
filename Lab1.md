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
- Employee: Đại diện cho nhân viên đang thực hiện thanh toán.
- PaymentMethod: Lớp mô tả phương thức thanh toán của nhân viên.
- BankSystemIntegration: Hệ thống tích hợp với ngân hàng để thực hiện thanh toán.
- Database: Lưu trữ thông tin thanh toán.
- Login: Lớp đảm bảo người dùng đăng nhập vào hệ thống.
## Sequence Diagram 
![Biểu đồ Sequence](https://www.planttext.com/api/plantuml/png/P591RiCW4BppYbLExI4VoA6ANFSGoLOikn_OmYf5mU02hkItzT0dzGi5RDmwER8pExCpukVh--WyMZ_sYhchr62D8uRS6mil_Q3CHCI6G91S3gWzx2fpaNe7wA3Q0WrEFMbVatyt8X6Q-evXZL8prcwn0lMrcvod_gGzNInwQMQReZjjgILwV4D72IqBnlAXi7-2wW3fmeT7Li4-33AupA4REIVdjbjDVO2E574FImoOSmIPfewCiZX0IzvA-gGR3YkBv1H5jiYw8MxisYZsCP9BVh4KU4R5HvLYiwQzitoLFN6q0b0BE5j15c8FgtTGZEz_ZhD81B8qPJEsWA7QSB8riP1yEWl3xDw5R_2NjYLkx9fstbsWH1JpwgRpJ5XC0kT8MiJVzWi00F__0m00)
## Một số thuộc tính và quan hệ giữa các lớp:
- Employee:
  - Thuộc tính: EmployeeID, Name, Position.
  - Quan hệ: Gửi yêu cầu thanh toán và chọn phương thức thanh toán.
- PaymentMethod:
  - Thuộc tính: PaymentType, AccountNumber.
  - Quan hệ: Liên kết với lớp BankSystemIntegration để thực hiện thanh toán.
- BankSystemIntegration:
  - Thuộc tính: TransactionID, BankName.
  - Quan hệ: Xử lý giao dịch và lưu trữ kết quả trong Database.
- Database:
  - Thuộc tính: PaymentHistory, AccountBalance.
  - Quan hệ: Lưu trữ thông tin liên quan đến thanh toán và người dùng.
- Payroll (Tính lương):
  - Thuộc tính: amount, payDate, payPeriod.
  - Quan hệ: Sử dụng lớp Timecard và Order để tính toán số giờ làm việc và doanh số cho việc tính lương, liên kết với lớp PaymentMethod để thực hiện thanh toán theo phương thức đã chọn.
## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/R55BRi8m5Dpx55wMHQvGqK8NB0eLS867FMeZ_47FBvKYr9DrmP6u0dLmKeZO-Ssy6SqydtzFqoJ4qdYdqhuEccE2CevIqc_-u68BwAFIkXh6nRmRb-JHFJwezGZo3lcALlseehw3YqN1jktXAdqn9ZP1betVWU-a79qhectjOOZjd8GwOCKMF4mpSgPn92Ygfyc_qIk5_QPD0hy8WaycgMFeit0qIAb4kbLbwnsbllT68gEihM4Ysx_bJAmXNECRjm57r13rwZzSjAgUHtSRKxcAwW-HiOTTrEE6URzleQO8Dd_l1G00__y30000)
# 4. Phân tích ca sử dụng Maintain Timecard
## Các lớp phân tích
- Employee: Quản lý thông tin nhân viên.
- Timecard: Ghi nhận số giờ làm việc của nhân viên.
- ProjectSystemIntegration: Lấy thông tin dự án để gán cho các bản ghi chấm công.
- Database: Lưu trữ thông tin về timecard và dự án.
## Sequence Diagram 
![Biểu đồ sequence](https://www.planttext.com/api/plantuml/png/L951JiCm44NtFiMeArZq0bcWAWcBI5bKTJZ0O0-LeROZUuhKix7WI5m1nuq3tiwR_-V9_ldwFaJ6m5Tx4V73E0W-aa35Fi2pdI_-HYJcj62KcT4nx4P_Dcu7666imMGiAGmwiwchuJ7uTr8iRv793exf792DlnSTvL1lzyZuYf4oxLiXYWhids1i83iyF8eHzcbGu3e7ULMAOgnJKzV0owoH2OfeAfYwXQNx3Po8Ww5FWbKL1lVcWysM8ctaKqlBVxwbz5hLjmt8z7X_LqJVRj4o0uabKlbl_6wgnO6SNhxc5m00__y30000)
## Một số thuộc tính và quan hệ giữa các lớp:
- Employee:
  - Thuộc tính: employeeID, name.
  - Quan hệ: Liên kết với Timecard để lưu thông tin chấm công của nhân viên.
- Timecard:
  - Thuộc tính: timecardID, employeeID, date, hoursWorked, chargeNumber.
  - Quan hệ: Liên kết với Employee để ghi nhận thông tin chấm công và với ProjectSystemIntegration để lấy thông tin về mã dự án.
- ProjectSystemIntegration:
  - Thuộc tính: projectID, chargeNumber.
  - Quan hệ: Liên kết với Timecard để đối chiếu mã dự án hoặc mã chi phí.
- Database:
  - Thuộc tính: timecardRecords, projectRecords.
  - Quan hệ: Lưu trữ thông tin chấm công và dữ liệu dự án.
## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/T90n3i8m34Ntd28Z3Bq2wb0akY14aPXDQr1e4oF7HQeG9sFWI5o1jgH136p-rl_VBtazdgaNO6bjetnjd6RogCe6lDTBUsceGzGtfNKIPPwDSWqMrLq5xyvOB86hu5rHotvFN6CrwWm4ns73TCPI-euO3QkYyu8sTu8d1Z7aGjKMXGrUSKgw8ytcttJV30Vm4sGXn3Z1V7pn6KcoY9mg0W_RVmY_hkcKIj5LmuUz0G00__y30000)
# 5. Hợp nhất kết quả phân tích
Hai ca sử dụng "Select Payment Method" và "Maintain Timecard" đều có chung những yêu cầu cơ bản về bảo mật (nhân viên phải đăng nhập trước khi sử dụng hệ thống), quản lý thông tin người dùng (Employee), và sự tích hợp với các hệ thống bên ngoài (hệ thống ngân hàng và hệ thống quản lý dự án).

## Các lớp chung
- Employee: Được dùng cho cả hai ca sử dụng.
- Database: Được dùng để lưu trữ cả thông tin phương thức thanh toán và thông tin timecard.
- ProjectSystemIntegration: Lấy thông tin dự án trong ca sử dụng Maintain Timecard.
- Login: Xác thực người dùng trước khi họ truy cập hệ thống.

## Tương tác
- Login xác thực người dùng trước khi truy cập hệ thống.
- Employee tương tác với Database để lưu trữ thông tin và tích hợp hệ thống bên ngoài.

