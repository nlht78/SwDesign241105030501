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
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/R551JiCm4Bpx5Jd28Lz0hPGKSO6AvWDBF0UBE8vsbwfHnSiuy2I-q3XsInIuxSxEx8pNFr_V6r5Y_V2TaNVN5nm4fkr8fDXQFm5dKnHbgf-gkNucZxdOWxqJSQ4NyscowXL3OCsor3JZa0IDyvX4BjYvhKXfBXxHWqcHw7VtlziYvOq4jttA3aVKVkZ22CJnH5-EeaTBRFyPlR05PtoLTnVOaoeu6wN-Rvxw5973A0gVgGbgmhxQPRyhKfzQT4cTRbcM3zdFv3D5vFh69RPAPTOf8sUPnMpGs_Y95m000F__0m00)
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
![Biểu đồ lớp](https://www.planttext.com/api/plantuml/png/R55BReD03DtFALWc2wvGKGc8kecYb0kuuCKe38Dijm95ELaMFLAk4EP3WaXszlDxzhmtj-j_nW8alwPLVD9TGfPHrIqm9v-DcO2pIf8qr5-vh_TWq1S79AEPjUrONLHK5QPlxOXunDwIH7begh4FmaeRdCJQDhxDGS0NE-oGGA9sitrk3KXfoO08KbmR-bTsCJZaUsH14wa1gkmXBoVc4Yc66jkbsZtd1nWVRnVI-8UpCJUEA-QHyrC3DN4qRGhPfUd7AW-rYiSnvdllPYlVQfs3lx1mgpBi6lUPTm000F__0m00)
# 3. Phân tích ca sử dụng Login
## Các lớp phân tích
## Sequence Diagram
## Một số thuộc tính và quan hệ giữa các lớp:
## Biểu đồ lớp
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

