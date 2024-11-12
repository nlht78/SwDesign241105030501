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
- Lớp Admin
  - Thuộc tính:
    - AdminID: Mã định danh duy nhất của Admin.
    - Name: Tên của Admin.
    - Permissions: Quyền hạn để tạo và xem báo cáo.
  - Quan hệ:
    - Kết nối một chiều với lớp Report: Admin sẽ khởi tạo và quản lý việc tạo báo cáo thông qua lớp Report.

- Lớp Report
  - Thuộc tính:
    - ReportType: Loại báo cáo (ví dụ: báo cáo nhân sự, báo cáo lương, báo cáo chấm công, v.v.).
    - TimePeriod: Khoảng thời gian của báo cáo (hàng tháng, hàng quý, hoặc hàng năm).
    - Data: Dữ liệu báo cáo, có thể là một tập hợp dữ liệu từ các bảng hoặc các lớp khác trong hệ thống.
  - Quan hệ:
    - Kết nối một chiều đến Database để lấy dữ liệu cần thiết.
    - Kết nối với ReportFormatter để định dạng dữ liệu thành báo cáo.
    - Có quan hệ với ExportSystem để xuất báo cáo sau khi định dạng.
   
- Lớp Database
  - Thuộc tính:
    - EmployeeData: Dữ liệu về nhân viên, gồm các thông tin cần thiết cho báo cáo.
    - TimecardData: Dữ liệu chấm công của nhân viên, cần thiết cho các báo cáo liên quan đến thời gian làm việc.
    - OrderData: Dữ liệu đơn hàng, cần cho các báo cáo liên quan đến doanh thu hoặc giao dịch.
  - Quan hệ:
    - Được truy xuất bởi lớp Report để thu thập các dữ liệu liên quan cho báo cáo.

- Lớp ReportFormatter
  - Quan hệ:
    - Nhận dữ liệu từ lớp Report và trả về một báo cáo đã định dạng sẵn.
    - Có quan hệ với ExportSystem để gửi báo cáo cho hệ thống xuất dữ liệu.

- Lớp ReportFormatter
  - Quan hệ:
    - Kết nối với ReportFormatter để nhận báo cáo đã định dạng và thực hiện xuất theo định dạng yêu cầu.
    - Trả về báo cáo đã được xuất tới Admin.
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
- Lớp EmployeeReport
  - Thuộc tính:
    - ReportType: Loại báo cáo (ví dụ: báo cáo chấm công, báo cáo hiệu suất).
    - TimePeriod: Khoảng thời gian cho báo cáo.
    - Data: Dữ liệu báo cáo, bao gồm thông tin về nhân viên và chấm công.
  - Quan hệ:
    - Kết nối với Database để lấy dữ liệu về nhân viên và chấm công.
    - Kết nối với ReportFormatter để định dạng báo cáo trước khi xuất ra.
    - Có quan hệ với ExportSystem để gửi báo cáo đã định dạng cho hệ thống xuất.

- Lớp ExportSystem
  - Quan hệ:
    - Nhận báo cáo đã định dạng từ ReportFormatter và thực hiện xuất theo định dạng yêu cầu.
    - Trả về báo cáo đã được xuất đến Admin.
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
- Lớp User:
  - Thuộc tính:
    - UserName: Tên đăng nhập của người dùng.
    - Password: Mật khẩu để xác thực người dùng.
- Quan hệ:
  - User và LoginSystem có quan hệ phụ thuộc: User gửi dữ liệu đăng nhập để LoginSystem xác thực.
  - LoginSystem và Database có quan hệ phụ thuộc: LoginSystem phụ thuộc vào dữ liệu xác thực từ Database để kiểm tra thông tin đăng nhập của người dùng.
## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/J8zD2W8n38NtEKMNkd2E82Ew5155zt4QjDWVQ3AAY2TpuP6yWcsjChiatylBo_lvQbamIkyiyDbu5GCJT1QPrOufgZieDIdb2XsLPftWDKGD3wZAPJWQlxsnaAiBUxH6ez0yaYOl1YsFneNCUZdbIPTejatZlyy21G_8L4qs9D7GfSWo-afBhAQP3g_2C45cFoTeoUlyt0S00F__0m00)
# 4. Phân tích ca sử dụng Maintain Employee Information
## Các lớp phân tích
- Payroll Administrator: Đại diện cho người quản trị hệ thống bảng lương, người có quyền thêm, sửa, hoặc xóa thông tin nhân viên.
- Employee: Chứa thông tin của từng nhân viên bao gồm tên, loại nhân viên, địa chỉ, số an sinh xã hội, thuế, mức lương, và các chi tiết khác.
- EmployeeManagementSystem: Quản lý quá trình thêm, cập nhật và xóa thông tin nhân viên.
- Database: Lưu trữ và truy xuất thông tin của nhân viên, hỗ trợ các thao tác thêm, sửa, hoặc xóa dữ liệu nhân viên.
## Sequence Diagram
![Squence Diagram](https://www.planttext.com/api/plantuml/png/p5H1JiCm4Bpx5QkUu53rtWDgYel4eI9gnGEMU8kiEdQmjqXv6mUUn1Umav0sKIlAZHmzipEpOojV7v-BmEZvK1eHzjg2Tu445kmyv5XxPqocIcrrO8_f40FacQZYY2vqXPPXiYehusgYDLfyfP8iR-l0L4uIURNU3jaI6LymK8FAfH1v1jExn9l3bWmL30y7Mx1s5cuofMRFbKAccOmO4_oOtGeq3147jFsXWFX5fIIOPtFOqDk10lSuFDgTyoKcyOPxuhsoJFuoirELotbZslCsL3Yl6efSmhHN6-9fXjGudjIXCbYVc4f19X2qA_zjC_dRGdAynuROQte_TWhfRYwlaj1-I8tjkipN53YcNjbXEwRQYhhdyFyhEabqx-nE-xBDVkO93d0QPrcZtn-TOhb3dRDvqWof8Pci4erib-gf8jzSK_IFSvGgNaHI-YLy0m00__y30000)

## Một số thuộc tính và quan hệ giữa các lớp:
- Lớp PayrollAdministrator:
  - Thuộc tính:
    - AdminID: ID quản trị viên bảng lương.
    - Permissions: Quyền thực hiện thao tác duy trì thông tin nhân viên.
- Lớp Employee:
  - Thuộc tính:
    - EmployeeID: ID của nhân viên (tạo tự động khi thêm mới).
    - Name: Tên nhân viên.
    - EmployeeType: Loại nhân viên (theo giờ, hưởng lương, có hoa hồng).
    - Address: Địa chỉ liên hệ.
    - SSN: Số an sinh xã hội.
    - TaxDeductions: Khấu trừ thuế tiêu chuẩn.
    - OtherDeductions: Các khoản khấu trừ khác (401k, bảo hiểm y tế).
    - PhoneNumber: Số điện thoại.
    - HourlyRate, Salary, CommissionRate, HourLimit: Tùy thuộc vào loại nhân viên.
- Quan hệ:
  - PayrollAdministrator và EmployeeManagementSystem có quan hệ phụ thuộc: PayrollAdministrator phụ thuộc vào EmployeeManagementSystem để thực hiện thêm, sửa, hoặc xóa nhân viên.
  - EmployeeManagementSystem và Database có quan hệ kết hợp: EmployeeManagementSystem sử dụng Database để lưu trữ, cập nhật, và truy xuất dữ liệu nhân viên
## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/h59BJiGm3Dtd55d2WZa26aIHG89IJOS3U2OM4v5FPRk8274o5Xo9Az26je8EmsfMiP-Vd-ENVBv_B5c0fFLEyPCDcYAZsZfWrXKaYivT66-3PI6GIFfLQNscCtPJvBX2yfRPni3gJGszLxvnCI4E_34TMahm-0jVfmO7OKF8dEEwBlEvXfS2JRkLFA97xcM7DCEgNGnOjdw3bFFhs99BAv1luHeSKChXPVJ3XQTgJxwrtih-1dSGu14z1gaJ2_h90JCoJaupyj2OJcu65kXm3roXaCNd2Iv0e2jDe_jy0poQLtU-poMECUpFzrqipW-khWvwyhFhVzQucrfYCFsl-m800F__0m00)
# 5. Phân tích ca sử dụng Maintain Purchase Order
## Các lớp phân tích
- CommissionedEmployee: Đại diện cho nhân viên làm việc theo hoa hồng, người có quyền thêm, cập nhật hoặc xóa thông tin đơn hàng để nhận hoa hồng.
- PurchaseOrder: Chứa thông tin về các đơn hàng bao gồm điểm liên hệ khách hàng, địa chỉ thanh toán, sản phẩm, ngày tạo và mã số đơn hàng duy nhất.
- OrderManagementSystem: Quản lý các thao tác thêm, cập nhật và xóa đơn hàng.
- Database: Lưu trữ và truy xuất thông tin đơn hàng, hỗ trợ các thao tác thêm, sửa và xóa dữ liệu đơn hàng.
## Sequence Diagram
![Squence Diagram](https://www.planttext.com/api/plantuml/png/v9I_JiCm4CPtFyMf4mmLUmTK6WU9eGfg1FiHNwb5R0Vx0igpCV18l09sKb2RLch5IXOhkj_z-UvB_FNnEG-CdbjJY_2YBNWNI635paFcZD4XQ6T9vQQfNKS4623BHHDJTAKRj0oJmYloIxJuJ8OibrrWCfD45ijo7vN8-8I1-gXS297bCBrEt0nAggbYk6rjnR4dN6IUaEdgeL7fa37C1FUjhpQn0lHTBmNM30C8E0eAY4yidJfa-GnMzDfIu145TtRjlC7Kiy_O6Ict784HBubHrs6tkbpCu4QfCRcYoddLWt81qv-g8oecaXhFAdLeQkmEPfM2wlWsxEJFYkLPGhVOZiOLiTVqDdO1agsdP2Rcjy2Utfv-9A_N7HJlbdpOw0RGAYWPkGtdxMOiQRkY4sRlY3kUS9w7GwuQpDb-gV_JdCpPjVPcMCAHNselJeSQZ3jKS9u7GyNeWLMYBxcTg6Z8zuQd2wqPc7c4qfNt3G00__y30000)
## Một số thuộc tính và quan hệ giữa các lớp:
- Lớp CommissionedEmployee:
  - Thuộc tính:
    - EmployeeID: ID của nhân viên hưởng hoa hồng.
    - Name: Tên nhân viên.
  - Quan hệ:
    - Phụ thuộc vào OrderManagementSystem để quản lý thông tin đơn hàng.
- Lớp PurchaseOrder:
  - Thuộc tính:
    - OrderID: Mã đơn hàng (tự động tạo khi thêm mới).
    - CustomerContact: Thông tin liên hệ khách hàng.
    - BillingAddress: Địa chỉ thanh toán của khách hàng.
    - ProductList: Danh sách sản phẩm được đặt hàng.
    - Date: Ngày tạo đơn hàng.
    - Status: Trạng thái đơn hàng (mở/đóng).
  - Quan hệ:
    - Kết hợp với OrderManagementSystem để lưu và quản lý đơn hàng.
- Lớp OrderManagementSystem:
  - Thuộc tính:
    - CreatePurchaseOrder(): Thêm mới đơn hàng.
    - UpdatePurchaseOrder(): Cập nhật thông tin đơn hàng.
    - DeletePurchaseOrder(): Xóa đơn hàng.
    - VerifyOwnership(): Kiểm tra quyền sở hữu của nhân viên đối với đơn hàng.
  - Quan hệ:
    - Kết hợp với Database để lưu trữ và truy xuất thông tin đơn hàng.
- Lớp Database:
  - Thuộc tính:
    - StorePurchaseOrder(): Lưu trữ đơn hàng mới.
    - UpdatePurchaseOrder(): Cập nhật thông tin đơn hàng.
    - DeletePurchaseOrder(): Xóa đơn hàng.
    - RetrievePurchaseOrderData(): Truy xuất thông tin đơn hàng dựa trên OrderID.
  - Quan hệ:
    - Kết hợp với OrderManagementSystem để quản lý lưu trữ và truy vấn dữ liệu.
## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/h5BBJiD03BplL-mH3lGJK27XW0IqQWJt9JkqA_OHsKvHXFWo3dmIlq2oJK6H0YTkjcVi6Nlty_rZoM98sk0LFxkeAJ5KxGspBb88Zjcb27iL6fywGByghS_qCRqkStfd0jIR6llMBTKxmrYH1OqDEHxPHSkI0gX8KKmjkNRfl7TnUs4jWJcNrfHiMykDumEbD88SL6AavH-zFFlMHBD5G9IgOq4OTGj2tpPnT7AQaVl6_eAKy9X77a3kgLkzH13lNDDNlqtqxinZJnzrAqdqRx8R23difzWWU30m-qwBnVdyOTJykGR-PFuVlEEkQebeXv_p1G00__y30000)
# 6. Phân tích ca sử dụng Run Payroll
## Các lớp phân tích
- PayrollScheduler: Khởi động quy trình trả lương định kỳ vào thứ Sáu hàng tuần và ngày làm việc cuối tháng.
- Employee: Đại diện cho nhân viên nhận lương, bao gồm thông tin như mức lương, phương thức thanh toán, và các khoản khấu trừ.
- PayrollCalculator: Thực hiện tính toán lương dựa trên thông tin chấm công, đơn hàng, thông tin nhân viên và các khoản khấu trừ theo luật.
- BankSystemIntegration: Hệ thống gửi yêu cầu giao dịch ngân hàng cho nhân viên nhận lương qua chuyển khoản.
- PayrollPrinter: In phiếu lương cho các phương thức nhận qua thư hoặc nhận trực tiếp.
- Database: Lưu trữ thông tin về nhân viên, bản chấm công, đơn hàng và trạng thái thanh toán.
## Sequence Diagram
![Squence Diagram](https://www.planttext.com/api/plantuml/png/R5D1JiCm4Bpx5Ilk_K0E2AK1gH8L5k43YxEbLXmxMhj8VHi7diGNM9lMJO58YQBCxCpkhFFryNaN4t8wJ4x5qNhW44cXIO7XHkEHWtFGcpqD1qTy0nX1zsgM2cliZ3vLrXgTEJYKmX_M-fhLOS9NZ5J0hhq6M_HZVuo9ferFzCQORF25sVQRVzqqMs6UhBHIkeVLhPWsiF4sMKm4v-ur1qCnAhtEbAvju9aIMtedk7VspRuwUPbc5uv4KNKjh4vAZpOc2Bi5g5m8Cpn8DeHcNm45SlqdVyBXnKvaa8S8w0Tuue4ubgA5MoNdfAh6iD3Eh7FATRo2bmUwb3zE935jAUt3q41dcKo2ZkOGRIgqYvvaAu9CMIrl05uOVPJTI_YLAgJQuWA7TV0xonDMChb8V_otQ1r8NDgQyJ3_yjUwWRB7N2P7p8mNWgwcP-o7UWg4_70zU4rlYppI03inxSZHrIoN5HLeiQ1dCe4lqlakvoNtq3U_Zv8CBuMKcxaJQlvtlW400F__0m00)
## Một số thuộc tính và quan hệ giữa các lớp:
- Lớp PayrollScheduler:
  - Thuộc tính:
    - Schedule: Thời gian chạy định kỳ của quy trình trả lương (thứ Sáu hàng tuần và ngày làm việc cuối tháng).
  - Quan hệ:
    - Kết hợp với PayrollCalculator để thực hiện tính toán lương cho nhân viên.
- Lớp Employee:
  - Thuộc tính:
    - EmployeeID: Mã định danh của nhân viên.
    - PaymentMethod: Phương thức thanh toán của nhân viên (chuyển khoản, nhận qua thư, hoặc nhận trực tiếp).
    - Salary, Benefits, Deductions: Thông tin lương, phúc lợi và các khoản khấu trừ.
  - Quan hệ:
    - Kết hợp với PayrollCalculator để nhận lương dựa trên các thông tin này.
- Lớp PayrollCalculator:
  - Quan hệ:
    - Kết hợp với Database để truy xuất dữ liệu, và phụ thuộc vào BankSystemIntegration và PayrollPrinter để thực hiện các giao dịch thanh toán.
- Lớp BankSystemIntegration:
  - Quan hệ:
    - Phụ thuộc vào PayrollCalculator để nhận các yêu cầu giao dịch thanh toán trực tiếp.
- Lớp PayrollPrinter:
  - Quan hệ:
    - Phụ thuộc vào PayrollCalculator để in phiếu lương.
- Lớp Database:
  - Quan hệ:
    - Kết hợp với PayrollCalculator để cung cấp dữ liệu cần thiết và lưu trữ thông tin lương.
## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/T591JiCm4Bpx5Jx2WJu1LIKSSW1Lj1zOd8LQMTkLlK6A42_Zm9Fu0hPZGr2QMoOpixCU-_lpQniOF0-6HEYrbTu558eW1Bc7qJkYWpfXDn1w-Iwal94LPz1QpHeOY_RgMdo8OhytPt8ZOh5Ls3OPFeAP9aIdGSiFo2VNJG50uCVykKEBBvf31asCLQoT3NyX9VSEI0q4xEgIzSUbnNPW-yCO64rh6Lyzf9drS6Yxn1yzs00vRMujq_PUHsVDoYWoiHVLpzKDC3n3g0qy8NkDRrYRI7IKpwcZDgZ0TpEgGKB-zKpZ5pUpsTmkgn3BSfAkZbgXwz8hzCNoLhJ_snBRs6rwPpy0003__mC0)
# 7 . Viết code Java mô phỏng ca sử dụng Maintain Timecard.
    package maintaintimecard;
  
    //Lớp đại diện cho Nhân viên
    class Employee {
     private String employeeID;
     private String name;
    
     public Employee(String employeeID, String name) {
         this.employeeID = employeeID;
         this.name = name;
     }
    
     public String getEmployeeID() {
         return employeeID;
     }
    
     public String getName() {
         return name;
     }
    }
    
    //Lớp đại diện cho Bản chấm công
    class Timecard {
     private String timecardID;
     private String employeeID;
     private String date;
     private double hoursWorked;
     private String projectID;
    
     public Timecard(String timecardID, String employeeID, String date, double hoursWorked, String projectID) {
         this.timecardID = timecardID;
         this.employeeID = employeeID;
         this.date = date;
         this.hoursWorked = hoursWorked;
         this.projectID = projectID;
     }
    
     public String getTimecardID() {
         return timecardID;
     }
    
     public String getEmployeeID() {
         return employeeID;
     }
    
     public String getDate() {
         return date;
     }
    
     public double getHoursWorked() {
         return hoursWorked;
     }
    
     public String getProjectID() {
         return projectID;
     }
    }
    
    //Lớp đại diện cho Tích hợp Hệ thống Dự án
    class ProjectSystemIntegration 
    {
     // Phương thức lấy thông tin dự án
     public String retrieveProjectInfo(String projectID) 
     {
         //  mô phỏng việc lấy thông tin dự án.
         // 
         System.out.println("Đang lấy thông tin cho Mã dự án: " + projectID);
         return "Thông tin Dự án cho " + projectID;
     }
    }
    
    //Lớp đại diện cho Cơ sở dữ liệu
    class Database 
    {
     //  mô phỏng cho việc lưu trữ các bản ghi chấm công và dự án.
     public void storeTimecard(Timecard timecard) 
     {
         System.out.println("Bản chấm công cho Mã nhân viên " + timecard.getEmployeeID() +
                 " vào Ngày " + timecard.getDate() + " đã được lưu trong Cơ sở dữ liệu.");
     }
    }
    
    //Mô phỏng Ca sử dụng cho Quản lý Chấm công
      public class MaintainTimecardSystem 
      {
      
       public static void main(String[] args) 
       
       {
         // Khởi tạo các thành phần hệ thống
         Employee employee = new Employee("E001", "John Doe");
         ProjectSystemIntegration projectSystem = new ProjectSystemIntegration();
         Database database = new Database();
    
         // Mô phỏng nhân viên đăng nhập
         System.out.println(employee.getName() + " đã đăng nhập thành công.");
    
         // Mô phỏng quy trình cập nhật chấm công
         String projectID = "P1234";
         String projectInfo = projectSystem.retrieveProjectInfo(projectID);
    
         // Tạo một bản ghi chấm công mới cho nhân viên
         Timecard timecard = new Timecard("TC001", employee.getEmployeeID(), "2023-10-01", 8.0, projectID);
    
         // Lưu bản chấm công vào cơ sở dữ liệu
         database.storeTimecard(timecard);
    
         // Thông báo cho nhân viên rằng cập nhật đã thành công
         System.out.println("Bản chấm công cho " + employee.getName() + " đã được cập nhật thành công.");
     }
    }
    
