# Bài tập 02 của sinh viên: K235480106081 - Nguyễn Thị Như Ý - Môn Hệ quản trị CSDL

## Bài toán

NỘI DUNG YÊU CẦU (GỒM 5 PHẦN):
Phần 1: Thiết kế và Khởi tạo Cấu trúc Dữ liệu (Kiến thức 6, 7)
Sinh viên tự chọn một chủ đề quản lý (Ví dụ: Quản lý thư viện, Quản lý khách sạn, hoặc Quản lý dự án, HOẶC BẤT KỲ BÀI TOÁN QUẢN LÝ NÀO KHÁC).

Tạo một Database mới với tên [Tên dự án]_[MaSV]. //LƯU Ý PHẢI CÓ MÃ SV CÁ NHÂN Ở TÊN CỦA DB ĐÚNG NHƯ YÊU CẦU, vd: QuanLyKhachSan_K123456789

Tạo ít nhất 3 bảng có quan hệ với nhau. Yêu cầu:

Sử dụng đa dạng các kiểu dữ liệu (Số nguyên, số thực, chuỗi ký tự Unicode, ngày tháng, tiền tệ, ...).

Áp dụng đúng quy tắc đặt tên (BướuLạcĐà).

Sử dụng cặp ngoặc [ ] để bọc tên bảng và tên trường trong script khởi tạo.

Có giải thích chỗ nào là PK, chỗ nào là FK, trường nào có ràng buộc cứng CK (ví dụ điểm từ 0..10),...

Phần 2: Xây dựng Function (Kiến thức 8, 9)
Hãy cho biết trong SQL Server có những loại function build_in (hàm có sẵn) nào, nêu 1 vài system function build_in mà em tìm hiểu được (ko cần nhiều, cần đặc sắc theo góc nhìn của em), cho SQL khai thác các hàm đó.

Hàm do người dùng tự viết trong SQL thường mang mục đích gì? Nó có những loại nào? Mỗi loại thường được dùng khi nào? Tại sao có nhiều system function rồi mà vẫn cần tự viết fn riêng?

Viết 01 Scalar Function (Hàm trả về một giá trị): Đưa ra 1 logic cho cơ sở dữ liệu của em, mà cần dùng đến function này. (SV TỰ NGHĨ RA YÊU CẦU CỦA HÀM VÀ VIẾT HÀM GIẢI QUYẾT NÓ)

Sau khi đã có hàm, viết câu lệnh sql khai thác hàm đó.

Viết 01 Inline Table-Valued Function: Trả về danh sách các bản ghi theo một điều kiện lọc cụ thể (SV TỰ NGHĨ RA YÊU CẦU CỦA HÀM VÀ VIẾT HÀM GIẢI QUYẾT NÓ)

Sau khi đã có hàm, viết câu lệnh sql khai thác hàm đó.

Viết 01 Multi-statement Table-Valued Function: Thực hiện xử lý logic phức tạp bên trong (có sử dụng biến bảng) trước khi trả về kết quả. (SV TỰ NGHĨ RA YÊU CẦU CỦA HÀM VÀ VIẾT HÀM GIẢI QUYẾT NÓ)

Sau khi đã có hàm, viết câu lệnh sql khai thác hàm đó.

Phần 3: Xây dựng Store Procedure (Kiến thức 10)
Trong SQL Server có những SP có sẵn nào? nêu 1 vài system sp mà em tìm hiểu được, giải thích cách dùng chúng.

Viết 01 Store Procedure đơn giản để thực hiện lệnh INSERT hoặc UPDATE dữ liệu, có kiểm tra điều kiện logic (SV TỰ NGHĨ RA YÊU CẦU CỦA SP VÀ VIẾT SP GIẢI QUYẾT NÓ)

Viết 01 Store Procedure có sử dụng tham số OUTPUT để trả về một giá trị tính toán (SV TỰ NGHĨ RA YÊU CẦU CỦA SP VÀ VIẾT SP GIẢI QUYẾT NÓ, SP NÀY CÓ DÙNG THAM SỐ LOẠI OUTPUT)

Viết 01 Store Procedure trả về một tập kết quả (Result set) từ lệnh SELECT sau khi đã join nhiều bảng. (SV TỰ NGHĨ RA YÊU CẦU CỦA SP VÀ VIẾT SP GIẢI QUYẾT NÓ)

Phần 4: Trigger và Xử lý logic nghiệp vụ (Kiến thức 11)
Viết 01 Trigger để tự động làm gì đó tại 1 bảng B khi mà dữ liệu thay đổi dữ liệu ở bảng A. Logic giải quyết do sv tự nghĩ ra, sao cho thực tế và thuyết phục.

Thử viết Trigger cho Bảng A : Khi insert thì cập nhật dữ liệu vào bảng B; sau đó viết trigger cho bảng B để khi B được cập nhật thì cập nhật sang bảng A : Quan sát các thông báo (nếu có) của hệ thống, giải thích các thông báo đó (nếu có). Đưa ra nhật xét cuối cùng về tình trạng này.

Phần 5: Cursor và Duyệt dữ liệu (Kiến thức 11)
Viết một đoạn script sử dụng CURSOR để duyệt qua danh sách của 1 câu lệnh SQL dạng SELECT, duyệt qua từng bản ghi, xử lý riêng từng bản ghi (THEO LOGIC SV TỰ ĐẶT RA: SAO CHO HỢP LÝ VÀ THUYẾT PHỤC)

Tìm cách không sử dụng CURSOR để giải quyết bài toán mà em đã dùng CURSOR mới giải quyết được ở trên. thử so sánh tốc độ giữa có dùng cursor và không dùng cursor (nếu cùng kết quả) thì thời gian xử lý cái nào nhanh hơn, cần ảnh chụp màn hình minh chứng.

Nếu vẫn tìm được cách dùng SQL để giải quyết vấn đề mà ko cần CURSOR: thử nghĩ bài toán khác, mà chỉ CURSOR mới giải quyết được, còn SQL rất khó giải quyết đc (theo logic suy nghĩ của em)


# Bài làm

## Phần 1: Thiết kế và Khởi tạo Cấu trúc Dữ liệu

Sử dụng lệnh create database để tạo database [QuanLyThuVien_K235480106081]

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-24 143500" src="https://github.com/user-attachments/assets/4710b942-eade-4446-ba8c-9fffcc954f9a" />

Bảng [DocGia]    MaDocGia → PK

Bảng [Sach]      MaSach → PK

Bảng [PhieuMuon] MaPhieu → PK

Bảng [PhieuMuon]  MaDocGia → FK liên kết tới DocGia(MaDocGia); MaSach → FK liên kết tới Sach(MaSach)

Bảng [Sach] SoLuong INT CHECK ([SoLuong] >= 0) Không cho số lượng âm

Bảng [PhieuMuon] TrangThai CHECK ([TrangThai] IN (N'Đang mượn', N'Đã trả')), Chỉ được nhập 2 trạng thái hợp lệ

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-24 143500" src="https://github.com/user-attachments/assets/304d5329-8acf-4600-84c8-72a440bdba19" />
            
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1be0e676-13d2-4598-9ccd-bf50137e6c2e" />

## Phần 2: Xây dựng Function

Các loại Built-in Function trong SQL Server:

  - Hàm xử lý chuỗi: LEN(), LOWER(), UPPER()

  - Hàm số học: ABS(), ROUND()

  - Hàm ngày tháng: GETDATE(), DATEDIFF()

  - Hàm chuyển đổi: CAST(), CONVERT()

  - Hàm hệ thống (System Function): @@VERSION, DB_NAME()

Một số hàm đặc sắc:

  - Hàm DATEDIFF() – tính khoảng cách thời gian

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ff199918-8fe9-4168-a2fb-0e23e46f2bb2" />

  - Hàm LEN() – đếm độ dài chuỗi

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4e54a5cf-4bb7-4245-a36e-3dd2eb84176c" />

  - Hàm GETDATE() – lấy ngày hiện tại

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/21f679b1-af4d-43d2-98a9-cd66a9384ef2" />

Hàm do người dùng tự viết trong SQL thường mang mục đích:

  - Đóng gói logic xử lý (ví dụ: tính tiền phạt, tính điểm, phân loại dữ liệu)

  - Tái sử dụng nhiều lần trong các câu lệnh SQL
  
  - Làm cho câu lệnh ngắn gọn, dễ hiểu hơn
  
  - Chuẩn hóa xử lý dữ liệu trong toàn hệ thống

Các loại hàm UDF trong SQL Server:

1. Scalar Function (Hàm vô hướng)

Trả về 1 giá trị duy nhất (INT, FLOAT, NVARCHAR,...)

Dùng khi:

  - Tính toán đơn giản
  - 
  - Xử lý từng giá trị riêng lẻ

2. Inline Table-Valued Function

  - Trả về 1 bảng (table)
    
  - Chỉ có 1 câu SELECT
    
  - Không có BEGIN...END

Dùng khi:

  - Lọc dữ liệu đơn giản

  - Thay thế VIEW có tham số

3. Multi-statement Table-Valued Function
   
  - Trả về bảng
    
Có thể:

  - Khai báo biến bảng

  - Xử lý nhiều bước (IF, CASE,...)

Dùng khi:

  - Logic phức tạp
    
  - Cần xử lý dữ liệu trước khi trả về

Tại sao có nhiều system function rồi mà vẫn cần tự viết fn riêng? -> Mặc dù SQL Server đã cung cấp nhiều hàm built-in, nhưng vẫn cần tự viết hàm vì các hàm có sẵn
chỉ xử lý chung, không đáp ứng được các nghiệp vụ đặc thù của từng hệ thống.

=>Hàm do người dùng định nghĩa giúp xử lý các nghiệp vụ đặc thù mà các hàm built-in không hỗ trợ. Việc sử dụng UDF giúp tăng tính tái sử dụng, giảm lặp code và làm cho hệ thống dễ bảo trì, mở rộng hơn.

Viết 01 Scalar Function (Hàm trả về một giá trị):

Ý tưởng: Tính tiền phạt nếu trả sách trễ -> Mỗi ngày trễ = 5000 VNĐ

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2d7f1842-b583-481c-8523-d755647521bd" />

Khai thác hàm scalar fn

Viết 01 Inline Table-Valued Function:

  - Ý tưởng: Lấy danh sách sách còn trong kho (SoLuong > 0)

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/315a1202-981a-4d9b-a46d-3de231e37ac9" />

Viết 01 Multi-statement Table-Valued Function:

  - Ý tưởng: Trả về danh sách phiếu mượn + tiền phạt + trạng thái nâng cao

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/64214307-9e81-4ca4-9b44-7732614bca85" />

## Phần 3: Xây dựng Store Procedure

Trong SQL Server có những SP có sẵn thường có tiền tố sp_, dùng để:

  - Quản lý database
    
  - Xem thông tin đối tượng
    
  - Hỗ trợ lập trình và quản trị

Một số System SP tiêu biểu:

  - sp_help – xem thông tin đối tượng

  Công dụng: Xem cấu trúc bảng (cột, kiểu dữ liệu), xem khóa chính (PK), khóa ngoại (FK)

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f8868c6c-f492-4bc5-8aeb-cfde29496df6" />

  - sp_helptext – xem nội dung code

  Công dụng: 
  
  Xem nội dung của: Function, Stored Procedure, View

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/99f362b7-2542-4b92-9caa-6e515d6791ab" />

- sp_columns – xem chi tiết cột

  Công dụng:

  Hiển thị chi tiết từng cột: Kiểu dữ liệu, Độ dài, Nullable

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/80f66129-a4be-4051-a496-972298c82476" />

Viết 01 Store Procedure đơn giản để thực hiện lệnh INSERT hoặc UPDATE dữ liệu, có kiểm tra điều kiện logic:

Yêu cầu:

Thêm đọc giả nhưng: Email phải chứa ký tự '@', không được trùng MaDocGia

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0050a257-d366-4ece-ab7b-49a9a8e502ed" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/be22900d-1253-42f7-9157-18fef15c17c1" />

Viết 01 Store Procedure có sử dụng tham số OUTPUT để trả về một giá trị tính toán

Yêu cầu: Tính tổng tiền phạt của 1 độc giả

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1f410197-4f60-4b51-915e-ac81a8653354" />

Viết 01 Store Procedure trả về một tập kết quả (Result set) từ lệnh SELECT sau khi đã join nhiều bảng

Yêu cầu:

Hiển thị danh sách phiếu mượn chi tiết, gồm: Mã phiếu, Tên độc giả, Tên mới, Ngày mượn, ngày trả, Tiền phạt

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/744d888e-ce74-459d-a44e-554da8a985dc" />

## Phần 4: Trigger và Xử lý logic nghiệp vụ

Viết 01 Trigger để tự động làm gì đó tại 1 bảng B khi mà dữ liệu thay đổi dữ liệu ở bảng A

  Trigger: Khi bảng A thay đổi → cập nhật bảng B

  - Ý tưởng: Khi có phiếu mượn mới (PhieuMuon) -> thì giảm số lượng sách (Sach)

   Giải thích: inserted: bảng tạm chứa dữ liệu vừa thêm. Khi mượn sách → số lượng sách giảm

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1c54cbf0-c78c-4ab5-98f8-e1f43ad82650" />


 Thử viết Trigger cho Bảng A : Khi insert thì cập nhật dữ liệu vào bảng B; sau đó viết trigger cho bảng B để khi B được cập nhật thì cập nhật sang bảng A : 

Trigger ngược lại (B → A)

  - Ý tưởng: Khi cập nhật bảng B → ảnh hưởng lại bảng A

 Ta cần làm: Khi cập nhật phiếu mượn  → cập nhật trạng thái số lượng sách

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/efb5e0ce-4ea0-4ce1-9c5d-d890aac02dcc" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/cc04dd00-75b6-4aff-b09e-c6a4a97d7201" />

Luồng xảy ra: Insert vào PhieuMuon; Trigger 1 chạy → giảm Sach; Sach bị UPDATE → Trigger 2 chạy → cập nhật lại PhieuMuon

## Phần 5: Cursor và Duyệt dữ liệu

Viết một đoạn script sử dụng CURSOR để duyệt qua danh sách của 1 câu lệnh SQL dạng SELECT, duyệt qua từng bản ghi, xử lý riêng từng bản ghi

Ý tưởng:

Duyệt từng phiếu mượn: Nếu trả trễ → cập nhật trạng thái = “Trễ hạn”; Nếu đúng hạn → “Đúng hạn”

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eae97a85-5ab3-4a6b-87b4-fe947f8c719e" />

Không sử dụng CURSOR để giải quyết bài toán mà em đã dùng CURSOR mới giải quyết được ở trên. thử so sánh tốc độ giữa có dùng cursor và không dùng cursor 

  - không dùng corsor

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2f4ee4b0-f686-4c25-aea4-cf1280315987" />

  - dùng corsor

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2cffd183-5456-49ed-8237-aaca0f41a82d" />

=> dùng corsor sẽ mất nhiều thời gian hơn dùng sql thường

Nếu vẫn tìm được cách dùng SQL để giải quyết vấn đề mà ko cần CURSOR: thử nghĩ bài toán khác, mà chỉ CURSOR mới giải quyết được, còn SQL rất khó giải quyết đc

Bài toán mà CURSOR phù hợp hơn

Ý tưởng:

  Gửi thông báo riêng cho từng độc giả: Nếu trễ → gửi cảnh báo; Nếu đúng hạn → gửi cảm ơn; Mỗi bản ghi có xử lý khác nhau + nhiều bước

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/43e5bbbd-c280-46ee-9ede-8f840402bbe8" />

=> Trong bài toán này, mỗi bản ghi cần được xử lý riêng biệt và tạo ra kết quả khác nhau, do đó việc sử dụng CURSOR là phù hợp hơn so với các câu lệnh SQL dạng tập hợp.
