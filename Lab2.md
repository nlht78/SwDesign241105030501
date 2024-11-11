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
- Payroll Administrator: Đại diện cho người quản trị hệ thống bảng lương, người có quyền thêm, sửa, hoặc xóa thông tin nhân viên.
- Employee: Chứa thông tin của từng nhân viên bao gồm tên, loại nhân viên, địa chỉ, số an sinh xã hội, thuế, mức lương, và các chi tiết khác.
- EmployeeManagementSystem: Quản lý quá trình thêm, cập nhật và xóa thông tin nhân viên.
- Database: Lưu trữ và truy xuất thông tin của nhân viên, hỗ trợ các thao tác thêm, sửa, hoặc xóa dữ liệu nhân viên.
## Sequence Diagram
![Squence Diagram](https://www.planttext.com/api/plantuml/png/p5H1JiCm4Bpx5QkUu53rtWDgYel4eI9gnGEMU8kiEdQmjqXv6mUUn1Umav0sKIlAZHmzipEpOojV7v-BmEZvK1eHzjg2Tu445kmyv5XxPqocIcrrO8_f40FacQZYY2vqXPPXiYehusgYDLfyfP8iR-l0L4uIURNU3jaI6LymK8FAfH1v1jExn9l3bWmL30y7Mx1s5cuofMRFbKAccOmO4_oOtGeq3147jFsXWFX5fIIOPtFOqDk10lSuFDgTyoKcyOPxuhsoJFuoirELotbZslCsL3Yl6efSmhHN6-9fXjGudjIXCbYVc4f19X2qA_zjC_dRGdAynuROQte_TWhfRYwlaj1-I8tjkipN53YcNjbXEwRQYhhdyFyhEabqx-nE-xBDVkO93d0QPrcZtn-TOhb3dRDvqWof8Pci4erib-gf8jzSK_IFSvGgNaHI-YLy0m00__y30000)

## Một số thuộc tính và quan hệ giữa các lớp:
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

## Biểu đồ lớp
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/T591JiCm4Bpx5Jx2WJu1LIKSSW1Lj1zOd8LQMTkLlK6A42_Zm9Fu0hPZGr2QMoOpixCU-_lpQniOF0-6HEYrbTu558eW1Bc7qJkYWpfXDn1w-Iwal94LPz1QpHeOY_RgMdo8OhytPt8ZOh5Ls3OPFeAP9aIdGSiFo2VNJG50uCVykKEBBvf31asCLQoT3NyX9VSEI0q4xEgIzSUbnNPW-yCO64rh6Lyzf9drS6Yxn1yzs00vRMujq_PUHsVDoYWoiHVLpzKDC3n3g0qy8NkDRrYRI7IKpwcZDgZ0TpEgGKB-zKpZ5pUpsTmkgn3BSfAkZbgXwz8hzCNoLhJ_snBRs6rwPpy0003__mC0)
# 7 . Viết code Java mô phỏng ca sử dụng Maintain Timecard.

