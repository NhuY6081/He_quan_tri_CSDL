# BT 3 - Nguyễn Thị Như Ý - K59KMT - K235480106081

## Bài làm

### Nhiệm vụ 1: Thiết kế CSDL

Tạo Data base QuanLyCamDo

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/70ae6027-dd55-4020-a1c2-bc9e36a63841" />

tạo các bảng chứa trường liên kết

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2985d2d3-c344-446a-a6bc-5a35d577776f" />

sơ đò thực thể liên kết

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-05-08 165110" src="https://github.com/user-attachments/assets/3f8b9524-95fd-4d44-922a-bb2db1372c1a" />

### Nhiệm vụ 2: Cài đặt SQL (Yêu cầu viết Scripts)

Event 1: Đăng ký hợp đồng mới (Vay tiền)

kịch bản:

Bước 1: Tiếp nhận khách hàng

Nhân viên nhập: Thông tin khách hàng; Danh sách tài sản cầm cố; Giá trị định giá từng tài sản; Số tiền khách muốn vay

Bước 2: Hệ thống kiểm tra: Khách hàng đã tồn tại chưa; Giá trị tài sản có đủ đảm bảo khoản vay không??

Bước 3: Tạo hợp đồng

Hệ thống:

- Sinh mã hợp đồng

- Ghi ngày vay

- Thiết lập:
    - Deadline1 → bắt đầu tính lãi kép
    - Deadline2 → cho phép thanh lý

Bước 4: Cập nhật trạng thái

- Hợp đồng: Đang vay

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d7296cd3-7362-4905-94a6-450f7006dc3e" />

- Tài sản: Đang cầm cố

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3aa3f49b-a97a-4808-8ee3-39a94a9756c7" />

Event 2 – Tính toán công nợ thời gian thực

Trường hợp 1: Chưa quá Deadline1

Input

- Ngày vay: 01/05

- Deadline1: 10/05

- Ngày kiểm tra: 18/05

Xử lý hệ thống:

- Tính số ngày vay

- Áp dụng lãi đơn

    - Công thức: Lãi = 5000/1tr + gốc + số ngày

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d49f1349-5e33-4714-82f2-7d3fc918aeb7" />

Trường hợp 2: Đã quá Deadline1

- Input

    - Ngày vay: 01/05

    - Deadline1: 10/05

    - Ngày kiểm tra: 20/05

- Xử lý
    - Giai đoạn 1: Tính lãi đơn đến Deadline1.

    - Giai đoạn 2:

      - Sau Deadline1: Chuyển sang lãi kép
      
      - Tính trên: Gốc + lãi đơn tích lũy

Hệ thống trả về:

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/66374a52-2d67-4814-89d7-7bb9c16bfda2" />

Event 3 – Xử lý trả nợ và hoàn trả tài sản

Trường hợp 1: Tài sản đã thanh lý

Điều kiện:

  - Ngày hiện tại > Deadline2
  
  - Và tài sản đã bán

Xử lý

Hệ thống: Từ chối nhận tiền, Không trả tài sản

Thông báo:Tài sản đã bán thanh lý, hợp đồng đã thanh lý.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3f555516-c639-4e5b-9f5e-b5fe5d8f2dd1" />

Trường hợp 2: Trả một phần tiền( aka trả góp)

Input

- Tổng nợ: 10 triệu

- Khách trả: 5 triệu

Xử lý

Hệ thống:

    - Trừ tiền vào công nợ
    
    - Ghi lịch sử thanh toán
    
Cập nhật trạng thái

Hợp đồng: Đang trả góp

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c89b414c-41a4-4c98-b085-87e92e30c9b4" />

Kiểm tra log thanh toán

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/beed70f2-2523-4bf1-bd8f-14284b5576df" />

Trường hợp 3: Trả hết nợ

Điều kiện: Tiền trả >= Tổng công nợ

Xử lý

  - Hệ thống:

    - Đóng hợp đồng
   
    - Trả toàn bộ tài sản
    
    - Cập nhật trạng thái

Hợp đồng: Đã thanh toán

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/67b0ce55-5b9e-49e9-89b9-5b519e87888e" />

Tài sản: Đã trả khách

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/94d92937-d182-4ee7-b278-ba744c9e75bd" />

Event 4 – Danh sách nợ xấu

Điều kiện lọc:Ngày hiện tại > Deadline1 và chưa thanh toán đủ

Hệ thống xuất:

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-05-08 193707" src="https://github.com/user-attachments/assets/a26da08e-c3c4-48c9-9e5b-808d31f0d219" />

Event 5 – Quản lý thanh lý tài sản

Trigger 1 – Chuyển trạng thái nợ xấu

Điều kiện: Ngày hiện tại > Deadline1

Xử lý tự động

Hệ thống đổi trạng thái: Đang vay → Quá hạn

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e441258e-d5de-47fc-aacd-84d936aa0c34" />

Trigger 2 – Sẵn sàng thanh lý

Điều kiện: Ngày hiện tại > Deadline2 và hợp đồng đang quá hạn

Xử lý tự động

  Tài sản: Đang cầm cố → Sẵn sàng thanh lý

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/11118fd0-4ba1-4e61-bd8e-cc85b29aca93" />

Trigger 3 – Đã bán thanh lý

Điều kiện: Nhân viên xác nhận bán tài sản. Xử lý tự động

Tài sản: Sẵn sàng thanh lý → Đã thanh lý

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-05-08 221312" src="https://github.com/user-attachments/assets/24edc541-f25e-40ac-a5a8-4fb323daafcf" />









