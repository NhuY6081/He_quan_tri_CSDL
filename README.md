# Bài tập môn Hệ quản trị cơ sở dữ liệu-TEE560, 

## YÊU CẦU BÀI TẬP #

1. Download và cài đặt SQL Server 2025, phiên bản Developer

   Link tải: https://www.microsoft.com/vi-vn/sql-server/sql-server-downloads 

   Chọn phiên bản *SQL Server 2025 Developer*

   Không chọn Azure (nặng, ko dùng đến), các tính năng mở rộng khác (feature) chọn tất cả   

   Cài đặt với 2 kiểu login (Mixed Mode): Windows Authentication (nhớ **Add Current User**) và SQL Server Authentication (username mặc định là **sa**, chỉ cần nhập mật khẩu **123** , nhớ nhập 2 chỗ: Enter password và Confirm password)
2. Cấu hình cho SQL Server làm việc ở cổng động (Dynamic Port), TCP: enable+active yes cho 127.0.0.1, chọn cổng động là 3xxxx với xxxx là **4 số cuối của mã số sv**, (nếu cổng này đã mở sẵn trước đó bởi 1 ứng dụng khác thì chọn cổng là 4xxxx hoặc 5xxxx)
3. Kiểm tra xem service SQL Server có đang running và mở đúng cổng đã chọn hay không?

   Sử dụng lệnh trên cmd: *netstat -ano | findstr LISTENING* để liệt kê các cổng mà máy tính đang mở,

   Nếu thấy dòng: **TCP    0.0.0.0:xxxxx**  với xxxxx là cổng đã chọn ở bước 2 là OK.
4. Cài đặt SQL Server Management Studio

   Link tải SSMS: https://learn.microsoft.com/en-us/ssms/install/install
5. Chạy phần mềm ssms để Đăng nhập vào SQL Server bằng 2 cách: Windows Authentication và SQL Server Authentication.

   Servername: localhost,xxxxx  (với xxxxx là cổng đã chọn ở bước 2)
6. Sử dụng giao diện đồ hoạ của ssms: Tạo cơ sở dữ liệu mới (create database) với tên tuỳ ý, chọn Path (nơi lưu trữ db) cho file lưu dữ liệu và file lưu log ở ổ đĩa khác với ổ C. mở path đã chọn xem 2 file đã tạo ra.
7. Sử dụng giao diện đồ hoạ của ssms: Tạo bảng dữ liệu (create and design table) với tên bảng tuỳ ý, có các trường dữ liệu phù hợp với dữ liệu của file [data mẫu (CSV)](./svtnut.csv?raw=true), với Khoá chính (Primary Key) là trường **masv**
8. Sử dụng giao diện đồ hoạ của ssms: Tìm cách import dữ liệu từ file mẫu vào trong bảng vừa tạo.
9. Mở cửa sổ mới để gõ lệnh trong ssms: GÕ lệnh để kiểm tra xem số dòng của bảng dữ liệu sau khi import, kết quả ok sẽ khoảng 12020 dòng.
10. Trong cửa sổ mới để gõ lệnh: Gõ lệnh để thêm (insert) 1 row vào bảng, với dữ liệu là thông tin cá nhân của sv đang làm bài (mỗi sv sẽ luôn khác nhau ở bước này). 
11. Trong cửa sổ mới để gõ lệnh: Gõ lệnh để cập nhật(update) trường noisinh thành 'Sao Hoả' cho những dòng có noisinh và diachi đều là NULL.
12. Sử dụng giao diện đồ hoạ của ssms: Tạo bảng **SaoHoa** gồm những sinh viên có nơi sinh ở 'Sao Hoả', keyword gợi ý: sử dụng 1 câu lệnh: SELECT + INTO
13. Trong cửa sổ mới để gõ lệnh: Gõ lệnh xoá (delete) trong bảng **SaoHoa** những sinh viên cùng họ với em, vd em họ nguyễn thì xoá những sv họ nguyễn.
14. Sử dụng giao diện đồ hoạ của ssms: Xuất toàn bộ kết quả của các bước 6,7,8,9,10,11,12,13 ra file **dulieu.sql** , keyword gợi ý: sử dụng tính năng GEN SCRIPT struct+data cho database
15. Sử dụng giao diện đồ hoạ của ssms: Xoá csdl đã tạo, sau khi xoá thành công, kiểm tra tại path (path chọn ở bước 6) xem còn tồn tại 2 file của bước 6 không?
16. Tạo cửa sổ mới để gõ lệnh: mở file **dulieu.sql** của bước 14, chạy toàn bộ các lệnh này. REFRESH lại cây liệt kê các database => kiểm chứng kết quả được tạo ra tương đương với các bước 6,7,8,9,10,11,12,13.
17. upload file **dulieu.sql** lên github repository của em (repository mà em đang edit file README.md)

18. Bài làm

 1.Cài đặt SQL Server 2025, phiên bản Developer

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-09 152350" src="https://github.com/user-attachments/assets/ad4c720b-50f5-4d15-b558-978dd714d337" />

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-09 152358" src="https://github.com/user-attachments/assets/e23a8a70-5d2f-4529-9fbe-764beab1a46b" />

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-09 152411" src="https://github.com/user-attachments/assets/fc05bf9b-df7b-4147-8bf1-1eb2c4771158" />

đã tải thành công SQL

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-09 153710" src="https://github.com/user-attachments/assets/e66c37be-72ee-472f-a6af-9afce444b9a0" />

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-09 154108" src="https://github.com/user-attachments/assets/da53ecad-6c5a-4eb5-9b2e-b3193e7735d8" />

2.Cấu hình cho SQL Server làm việc ở cổng động (Dynamic Port)

<img width="1018" height="789" alt="Ảnh chụp màn hình 2026-04-09 155839" src="https://github.com/user-attachments/assets/8519b698-5991-4e1e-9aa0-517943c0b051" />

<img width="834" height="762" alt="Ảnh chụp màn hình 2026-04-09 161354" src="https://github.com/user-attachments/assets/916db179-88c3-467d-993d-b5408acbd5a8" />

3.Kiểm tra service SQL Server đang running và mở đúng cổng đã chọn

<img width="1167" height="309" alt="Ảnh chụp màn hình 2026-04-09 161601" src="https://github.com/user-attachments/assets/48945d52-ae14-47d2-8ca8-236b5f4d57b0" />

4.Cài đặt SQL Server Management Studio

<img width="1174" height="760" alt="image" src="https://github.com/user-attachments/assets/4427fbd0-682d-4e10-bb0d-fcd5d0934f00" />

5.Chạy phần mềm ssms để Đăng nhập vào SQL Server bằng 2 cách: Windows Authentication và SQL Server Authentication.

<img width="679" height="783" alt="image" src="https://github.com/user-attachments/assets/2d959b4c-927d-4c14-8f00-282a2c40c672" />

<img width="430" height="294" alt="image" src="https://github.com/user-attachments/assets/6cc5e04e-3da4-42ef-82fb-4050fab02226" />

6.Tạo cơ sở dữ liệu mới và nơi lưu file

<img width="1143" height="851" alt="Ảnh chụp màn hình 2026-04-09 162107" src="https://github.com/user-attachments/assets/e0d510c7-f4cb-44ee-8b5f-d3f87b8ace42" />

7.Tạo bảng sinh viên với các trường dữ liệu theo file mẫu

<img width="1218" height="508" alt="Ảnh chụp màn hình 2026-04-09 164745" src="https://github.com/user-attachments/assets/341771f1-75c6-4ae3-aa88-d0ff1b6133c3" />

8.import dữ liệu từ file mẫu vào trong bảng

<img width="1765" height="946" alt="Ảnh chụp màn hình 2026-04-09 175159" src="https://github.com/user-attachments/assets/a2905363-2d89-4691-acdc-c9ff250b305d" />

9.kiểm tra xem số dòng của bảng dữ liệu sau khi import

<img width="821" height="583" alt="Ảnh chụp màn hình 2026-04-09 175331" src="https://github.com/user-attachments/assets/3246a21f-e1aa-48b9-b2f4-5a8c6f1f2d4b" />

10.Gõ lệnh để thêm (insert) 1 row vào bảng, với dữ liệu là thông tin cá nhân của sv

<img width="1054" height="572" alt="Ảnh chụp màn hình 2026-04-09 180002" src="https://github.com/user-attachments/assets/a4fd38f9-0539-45d5-a802-497c4a41fde7" />

11.cập nhật(update) trường noisinh thành 'Sao Hoả' cho những dòng có noisinh và diachi đều là NULL.

<img width="1375" height="819" alt="Ảnh chụp màn hình 2026-04-09 185910" src="https://github.com/user-attachments/assets/1dfb23ac-dd5b-402c-bac7-35492b73505d" />

12.Tạo bảng **SaoHoa** gồm những sinh viên có nơi sinh ở 'Sao Hoả'

<img width="967" height="836" alt="Ảnh chụp màn hình 2026-04-09 190311" src="https://github.com/user-attachments/assets/7f6e7fca-edc4-47d6-9c4b-b2a1f57a39d7" />

13.xoá (delete) trong bảng **SaoHoa** những sinh viên cùng họ với em

<img width="967" height="836" alt="Ảnh chụp màn hình 2026-04-09 190311" src="https://github.com/user-attachments/assets/f4b22087-22d2-40e7-8cfc-b5b4f45813b4" />

14.Xuất toàn bộ kết quả của các bước 6,7,8,9,10,11,12,13 ra file **dulieu.sql*

<img width="1374" height="798" alt="image" src="https://github.com/user-attachments/assets/8ae16558-469b-4d08-8b2c-632a1eea3159" />

15.Xoá csdl đã tạo

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-09 191540" src="https://github.com/user-attachments/assets/91193990-584b-465f-b5ab-ccf78e6f87db" />

kiểm tra tại path (path chọn ở bước 6) không còn 2 file đã taoh ở bước 6

<img width="1013" height="367" alt="image" src="https://github.com/user-attachments/assets/898ab639-6e78-4cf7-aad1-046bd1b3473d" />

16.REFRESH lại cây liệt kê các database => kiểm chứng kết quả được tạo ra tương đương với các bước 6,7,8,9,10,11,12,13.

<img width="1920" height="1080" alt="Ảnh chụp màn hình 2026-04-09 194350" src="https://github.com/user-attachments/assets/93ea4359-c24c-4883-9aa9-ac80157f6c13" />
