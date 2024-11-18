1. Describe Interaction Among Design Objects
Các đối tượng thiết kế:

Actor: Any User
Người dùng nhập thông tin đăng nhập và nhận phản hồi từ hệ thống.
Boundary Object: LoginForm
Là giao diện chính mà người dùng tương tác để gửi thông tin đăng nhập.
Controller Object: LoginController
Xử lý logic ứng dụng, nhận thông tin từ LoginForm và xác thực thông qua các dịch vụ khác.
Entity Object: UserAccount
Đại diện cho thông tin tài khoản người dùng được lưu trữ trong hệ thống.
Subsystem: AuthenticationService
Thực hiện kiểm tra thông tin đăng nhập và trả về kết quả xác thực.
Luồng tương tác chính:

User tương tác với LoginForm để nhập username và password.
LoginForm chuyển thông tin này đến LoginController.
LoginController gọi AuthenticationService để xác thực username và password dựa trên dữ liệu từ UserAccount.
AuthenticationService trả kết quả cho LoginController.
LoginController phản hồi cho LoginForm:
Nếu thông tin chính xác, hiển thị trang Dashboard.
Nếu thông tin sai, hiển thị thông báo lỗi.
2. Simplify Sequence Diagrams Using Subsystems
3. Describe Persistence-Related Behavior
Persistence-Related Classes:

UserAccount: Lưu trữ thông tin tài khoản của người dùng như username, passwordHash, và status (e.g., active, locked).
UserRepository: Một lớp DAO (Data Access Object) thực hiện các hành động như:
Lấy thông tin tài khoản từ cơ sở dữ liệu dựa trên username.
Kiểm tra trạng thái tài khoản.
Lưu lại thông tin đăng nhập thất bại nếu cần (audit logs).
Quy trình xử lý dữ liệu:

LoginController gọi UserRepository để truy xuất thông tin tài khoản người dùng.
UserRepository truy xuất từ cơ sở dữ liệu, trả về thông tin tài khoản.
AuthenticationService kiểm tra passwordHash và trạng thái tài khoản.
Kết quả xác thực được trả về và sử dụng để cập nhật giao diện người dùng.

4. Refine the Flow of Events Description
5. Unify Classes and Subsystems


