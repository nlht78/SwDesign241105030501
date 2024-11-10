# 1. Phân tích ca sử dụng Create Administrative Report:
## Các lớp phân tích
- Admin: Người có quyền tạo các báo cáo quản trị và xem thông tin báo cáo.
- Report: Lớp quản lý các thông tin liên quan đến báo cáo như thời gian, loại báo cáo, và dữ liệu liên quan.
- Database: Hệ thống lưu trữ các dữ liệu cần thiết cho báo cáo như thông tin nhân viên, chấm công, và đơn hàng.
- ReportFormatter: Định dạng báo cáo theo mẫu định sẵn.
- ExportSystem: Xử lý xuất báo cáo ra các định dạng như PDF, Excel.
## Sequence Diagram
![Squence Diagram](https://www.planttext.com/api/plantuml/png/R94xRiCm44HxdcBXAYvy0HQ1hKYgX1Ja2HXf4H29I7cvokTiAN8aNy7yI844f2DdvYrtmDlFxpcm8Px7Tn7Uh0Fo0ONfsHDSXj4wCKNNzdOoZk7G-LVh3c02T7j3uUI9iwFsJctOl9Y0sQkh_x3MqsYOaGhVxZFDLyhexy0uva2ZXSYxmUaHEWbvgOUZwE0KXUmi8kYvxp64JLv9U28qZF2Cdr3UZwnANbt9g31P_C1ukCwMS81KGDHL7XxfTFrB3QAGgfLGMcn6jYjI95Xhhb2Z9PHoIq8qUbjXmKeaKcTqG_gdEm000F__0m00)
## Một số thuộc tính và quan hệ giữa các lớp:

## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/R551JiCm4Bpx5JdI0tq2QgMaY0kj81zOuZbOn76qkwqQ8Lx6WIVr2urZ5wB0RNTsPcUyldnzRqI9zUXR8--kApW8JDEIIB6rVWG-J57Sf_gfdEfdyfYA0zWx4HSwCPycgrxG1zOiIqqzz4bGEuzHv8ATsfAKfk8H7PWKYNwt-jqMAMya-Dcdx712vVis340SZ_JvA7eqnFQVqPujEEEBlBl0dbJ1sIZrV_DKvuYy3gBmcPgWEXpANVQx8TMvGPlKwPRhzKFsC_bC4RczSOujKfbboiYPPp4RT3P-uXK00F__0m00)
# 2. Phân tích ca sử dụng Create Employee Report
## Các lớp phân tích
- Admin: Quản lý thông tin Admin và quyền tạo báo cáo nhân viên.
- EmployeeReport: Quản lý việc tạo báo cáo liên quan đến thông tin nhân viên, bao gồm dữ liệu cá nhân và hiệu suất làm việc.
- Database: Lưu trữ dữ liệu về nhân viên và các bản ghi chấm công liên quan để hỗ trợ tạo báo cáo.
- ReportFormatter: Định dạng báo cáo theo các tiêu chuẩn trước khi xuất ra.
- ExportSystem: Hỗ trợ xuất báo cáo sang các định dạng (PDF, Excel) theo yêu cầu.
## Sequence Diagram
![Squence Diagram](https://www.planttext.com/api/plantuml/png/P98zJiGm44PxdsAqLRPOqQT0IvI49WMoJs2I4R98xCYUeDspKN0ahe3_WXnevtl-_3poz-VNrP6qj2qpS-zAWpKEcHp9M7YQ5gNPwbCrgbLgWjDWtfG-WNGm78DkMMTpH-Iu6akHwFWHIL5lx2A9q4Q6ztzgRe4HTqUuf19n15f9ybKwZ67RC1ObuV88GmtHhZgp0Iv-49Cy1B6D8pfNy1sluHarMaa8kpuaIT_HyG2rJUr7P1L-552GO6qJRmarX-2Ndt87xsj8hyxjZFUxW6Stgs5VohGJXQRm_N4hEOCgqLvH53L9yLzHKCWj-NYX9yezvJZTvGkgbxP_w6uZpcTsHJs57_83003__mC0)
## Một số thuộc tính và quan hệ giữa các lớp:
## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/R55BReD03DtFALYcYt24Y4X0rKs56YxWWXUZCWootGWKzMHTz4YzGkP7YsXtzlDxzhmttvzV1GkGl9j1yPiUCxACgXk0EJltnW4tbMN7M3-LeNu6Ww5ea8ncrdPazQ6IgZBJO1V45vmiIPB7fbscA6orGIVMjWzj2GAXUCGH2IHf3m-_MoDIMp8WWfJMnlulkvezSbbOq2HgX5hRbBLZRf5gxd3OglrpNe7nv-r26g-u6lFZj68TUJyTK9z6RbFCBizFkppKBXxFME_zDzlvLliSmeMDMrNWsFlFl0C00F__0m00)
# 3. Phân tích ca sử dụng Login
## Các lớp phân tích
- User: Đại diện cho người dùng muốn truy cập vào hệ thống. Người dùng sẽ có thuộc tính như tên người dùng và mật khẩu.
- LoginSystem: Quản lý quá trình xác thực người dùng, kiểm tra tên người dùng và mật khẩu, và cho phép đăng nhập nếu thông tin hợp lệ.
- Database: Lưu trữ thông tin tài khoản người dùng, bao gồm tên người dùng và mật khẩu đã mã hóa, để so sánh với dữ liệu đầu vào và xác thực.
## Sequence Diagram
![Squence Diagram](https://www.planttext.com/api/plantuml/png/R951QiCm44NtEiMGVIxWHGb6MHJSKYfQo78YJrDHMJAQSKBEraMFr2jKSeoBMsiX4F_D_r_Iz-VNZWMJ39rN_E42fCYaq4fCyCAKL9z5PrsFGM3Jn9CBnYQYi05aQCoQVcMXRj8FVmYDWaTa6cLTArL2O7kNqGhsGVBX4Ji232qy8VCbfbOrvaOSCcE6O-S4nYGeRagX5tX5xzgLKSYh31O3NLVmJ98SdMcyt6s-8Bg6xHmnIpEzz2bLpNkyJ2NCO2qnJyZeKnogfVmsU4MU2Ux3-RThVkNLgYL2E-uzNc6VKiOUiWUUw7_As6J9K6ZLBc_bKty0003__mC0)
## Một số thuộc tính và quan hệ giữa các lớp:
## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/J8zD2W8n38NtEKMNkd2E82Ew5155zt4QjDWVQ3AAY2TpuP6yWcsjChiatylBo_lvQbamIkyiyDbu5GCJT1QPrOufgZieDIdb2XsLPftWDKGD3wZAPJWQlxsnaAiBUxH6ez0yaYOl1YsFneNCUZdbIPTejatZlyy21G_8L4qs9D7GfSWo-afBhAQP3g_2C45cFoTeoUlyt0S00F__0m00)
# 4. Phân tích ca sử dụng Maintain Employee Information
## Các lớp phân tích
## Sequence Diagram
## Một số thuộc tính và quan hệ giữa các lớp:
## Biểu đồ lớp
# 5. Phân tích ca sử dụng Maintain Purchase Order
## Các lớp phân tích
## Sequence Diagram
## Một số thuộc tính và quan hệ giữa các lớp:
## Biểu đồ lớp
# 6. Phân tích ca sử dụng Run Payroll
## Các lớp phân tích
## Sequence Diagram
## Một số thuộc tính và quan hệ giữa các lớp:
## Biểu đồ lớp
# 7 . Viết code Java mô phỏng ca sử dụng Maintain Timecard.

