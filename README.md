![Untitled3](https://github.com/user-attachments/assets/142ff103-3a96-4d63-802e-4d117bde1174)
 # Bài tập 6: Hệ quản trị CSDL
# Chủ đề: Câu lệnh Select
Yêu cầu bài tập: 
Cho file sv_tnut.sql (1.6MB)
# ĐỀ BÀI:
1. Hãy nêu các bước để import được dữ liệu trong sv_tnut.sql vào sql server của em
2. dữ liệu đầu vào là tên của sv; sđt; ngày, tháng, năm sinh của sinh viên (của sv đang làm bài tập này)
3. nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?
4. nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?
5. nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?
6. nhập sql để tìm xem có những sv nào trùng tên với em?
7. nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.
8. nhập sql để tìm xem có những sv nào có sđt sai khác chỉ 1 số so với sđt của em.
9. BẢNG SV CÓ HƠN 9000 ROWS, HÃY LIỆT KÊ TẤT CẢ CÁC SV NGÀNH KMT, SẮP XẾP THEO TÊN VÀ HỌ ĐỆM, KIỂU TIẾNG  VIỆT, GIẢI THÍCH.
10. HÃY NHẬP SQL ĐỂ LIỆT KÊ CÁC SV NỮ NGÀNH KMT CÓ TRONG BẢNG SV (TRÌNH BÀY QUÁ TRÌNH SUY NGHĨ VÀ GIẢI NHỮNG VỨNG MẮC)

Bài Làm
1. Hãy nêu các bước để import được dữ liệu trong sv_tnut.sql vào sql server của em  
- để import dữ liệu từ file sv_tnut.sql vào CSDL của sinh viên rất đơn giản  
  Ở phần USE [nhap_ten_CSDL] muốn import dữu liệu từ file có sẵn vàO CSDL của bản thân + Bấm Execute để chạy  
Sau khi chạy nó sẽ tạo ra bảng SV + dữ liệu có sẵn  như hình dưới  
![Untitled0](https://github.com/user-attachments/assets/31f8d7ce-cf2f-497a-bbf4-6d85dc2e9d7a)  

2. dữ liệu đầu vào là tên của sv; sđt; ngày, tháng, năm sinh của sinh viên (của sv đang làm bài tập này  
    Thêm dữ liệu đầu vào ta tạo thêm một db.SinhVien với các trường dữ liệu, kiểu dữ liệu   
   với dữ liệu đầu vào là (ten_sv, sdt, ngay_sinh,...)   
   CLick chuột vào db.SinhVien mở Edit Top 200 Row để nhập dữ liệu demo cho bảng như hình dưới.  
![Untitled2](https://github.com/user-attachments/assets/a7f06552-3ebb-43c8-81b8-7d10dd310566)

3. nhập sql để tìm xem có những sv nào trùng hoàn toàn ngày/tháng/năm với em?  
 Open New Query để nhập câu lệnh truy vấn xem có sv nào có cùng Ns với sv đang làm bài tập    
Sử dụng câu lệch Select * From đến bảng SV      
Where ns = 'nam_thang_ngay'     
 sau đó Execute để chạy     
![Untitled3](https://github.com/user-attachments/assets/327a2192-573f-47de-b0d4-6b276446d28c)

4. nhập sql để tìm xem có những sv nào trùng ngày và tháng sinh với em?  
  Sử dụng câu lệch select và 2 hàm DAY , MONTH để tìm những người có cùng ngày sinh, tháng sinh với sv  
![Untitled4](https://github.com/user-attachments/assets/52eebda8-d1ae-4da0-a42d-26fff339fcb8)  


5. nhập sql để tìm xem có những sv nào trùng tháng và năm sinh với em?   
Tương tự như tìm những sv cùng ngày/tháng sinh    
Tìm ns/năm sinh cũng như vậy dùng hàm DAY để tìm NS, YEAR (năm sinh)   
![Untitled5](https://github.com/user-attachments/assets/35773a83-1e62-4a8b-9e29-b4e561d8b4e8)


6. nhập sql để tìm xem có những sv nào trùng tên với em?
WHERE ten để tìm những người tên dương với 185 rows tên dương
![Untitled6](https://github.com/user-attachments/assets/3e99cc3f-7b90-4ffe-b8be-678020eecb7b)

7. nhập sql để tìm xem có những sv nào trùng họ và tên đệm với em.
WHERE hodem nhập hodem cần tìmta được 50 rows 'Nguyễn Thế'
![Untitled7](https://github.com/user-attachments/assets/43a45a65-d8f2-4996-a8c7-27127eb24847)

8. nhập sql để tìm xem có những sv nào có sđt khác chỉ 1 số so với sđt của em.

9. BẢNG SV CÓ HƠN 9000 ROWS, HÃY LIỆT KÊ TẤT CẢ CÁC SV NGÀNH KMT, SẮP XẾP THEO TÊN VÀ HỌ ĐỆM, KIỂU TIẾNG  VIỆT, GIẢI THÍCH.
WHERE lop LIKE '%KMT%':   Chỉ lấy các sinh viên thuộc lớp có chứa từ "KMT" trong tên lớp.  
ORDER BY ten, ho_dem:  Truy vấn sẽ sắp xếp dữ liệu trước hết theo cột ten (Tên), và sau đó theo cột ho_dem (Họ đệm).      
COLLATE Vietnamese_CI_AS: Vietnamese_CI_AS là Collation hỗ trợ sắp xếp theo bảng chữ cái tiếng Việt (bao gồm cả dấu câu và ký tự tiếng Việt). Điều này rất quan trọng để đảm bảo kết quả sắp xếp chính xác với ngôn ngữ tiếng Việt.   
![Untitled9](https://github.com/user-attachments/assets/ed76a863-d7fc-4a8b-987f-627a0d013064)


