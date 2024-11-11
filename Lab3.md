# 1.	Subsystem context diagrams

## Biểu đồ ngữ cảnh 
### PrintService
![Biểu đồ ngữ cảnh](https://www.planttext.com/api/plantuml/png/Z951JWCn34NtFeNLJSjYBb2DHfKg5kmGFK4OZ1erJQQs1n4LJiQYH-eL60-DXfODMLdVty_-oldhj19rhFq-WEnyH4v2CCT7bpc5WEiKrGfYQ8CJAOr9noFW-BYFb-RY3Zx18EoZueRupRU4c_vPiYZjOL29NzsWFOoMuYYapiH5vtAxfNQ7IriwbiQzdF5xhgwbi8VPz9wRvd-iuSRxg5upherACeKSFMPuek3KfoXRtmdyZLzLpKsC9SwO3Zs9_cp7idq6ryRwewgkajpq3JsTigBuOj_q3G00__y30000)

Giải Thích cho PrintService
- PayrollController: Đây là thành phần điều phối việc in phiếu lương và gửi yêu cầu in tới PrintService.

- IPrintService: Đây là interface của PrintService giúp đảm bảo tính trừu tượng. PayrollController tương tác với IPrintService để in phiếu lương.

- PrintService: Đây là hệ thống con thực tế thực hiện việc in phiếu lương (paycheck).

- Paycheck: Đây là đối tượng phiếu lương cần được in ra. PrintService sẽ nhận Paycheck từ PayrollController thông qua IPrintService và in nó.

### ProjectManagementDatabase subsystems
![Biểu đồ ngữ cảnh](https://www.planttext.com/api/plantuml/png/Z95DJiD038NtFeNL3MMH2rHHLAbbqGKIWXEumOM1YQUo7KG4d8m5H-8AT4fI_eBKMOtc-RtFzho_litDIRrj8jXz4DHa32TuGPsc676HnFE55Uf8PeFmzOvFWFkZhVJYz1HU88TekkFQyPo4RhXXSRngrzQPSmD1d7L3DUEgh_jMTiXary0FFDr-bgoME1jYCwJlwRT_IKvhCiQoj068kuZ7hggEpjuDS2OUlCD5fh3zf6NzaYDvI6AtOMlmTpL5KOrDDyF90CSUZa4sIPjzsWH6FELpKVm_w9WZmm-zpbckynz_0000__y30000)

Giải Thích cho ProjectManagementDatabase
- PayrollController: Thành phần điều phối việc lấy thông tin dự án cho quá trình tính lương.

- IProjectManagement: Interface của ProjectManagementDatabase qua đó PayrollController lấy thông tin dự án.

- ProjectManagementDatabase: Hệ thống con thực tế lưu trữ và cung cấp thông tin dự án của nhân viên.

- Project: Đối tượng dự án được ProjectManagementDatabase lưu trữ và truy xuất để hỗ trợ tính lương.

