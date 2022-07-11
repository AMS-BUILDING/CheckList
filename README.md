# General Rules — Naming Conventions- FE- BE

## I. Database
### 1. Table Name
- Sử dụng chữ thường:  Sẽ giúp nhập liệu nhanh hơn, tránh mắc lỗi phân biệt chữ hoa chữ thường , v.v.
- Không có khoảng trắng - thay vào đó hãy sử dụng dấu gạch dưới
- Không có số trong tên chỉ có ký tự tiếng Anh alpha
- Tên hợp lệ dễ hiểu như blog, company, ...
- Tên không được nhiều hơn 64 ký tự.
- Tên bảng có thể là số ít
- Thêm tiền tố cho tên bảng. 
    - Đối với các bảng đơn lẻ thêm tiền tố 't_'. Ví dụ: t_company
    - Đối với các bảng liên kết thêm tiền tố 'r_'. Ví dụ: r_company_employee
### 2. Column Name
- Chọn ngắn gọn và một hoặc hai từ càng tốt.
- Tên trường phải dễ hiểu, ví dụ: price, company_name, v.v.
- Tên cột chính: Khóa chính có thể là id hoặc tên bảng _id. Nó phụ thuộc vào sự lựa chọn của riêng bạn nhưng đối với tôi, tôi thích id như nó tự giải thích.
- Tránh sử dụng từ dự trữ làm tên trường: order, date là những từ dành riêng cho cơ sở dữ liệu tránh sử dụng nó. Bạn có thể thêm tiền tố vào những tên này để dễ hiểu như user_name, signup_date, v.v.
- Tránh sử dụng cột trùng tên với tên bảng. Điều này có thể gây nhầm lẫn trong khi viết truy vấn.
- Xác định khóa ngoại trên lược đồ cơ sở dữ liệu.
- Tránh các tên viết tắt, nối liền hoặc dựa trên từ viết tắt
- Cột khóa ngoại phải có tên bảng với khóa chính của chúng, ví dụ: blog_id đại diện cho id khóa ngoại từ blog bảng.
- Tránh các tên khóa chính có ý nghĩa về mặt ngữ nghĩa. Một lỗi thiết kế cổ điển là tạo một bảng có khóa chính có ý nghĩa thực tế như 'name' làm khóa chính. Trong trường hợp này nếu một số người thay đổi tên của mình thì mối quan hệ với bảng khác sẽ có hiệu lực và tên có thể lặp lại (không phải duy nhất).

## II. Controller(BE)
- Tạo class Controller theo chức năng trên từng màn hình trên Admin.
- Quy ước đặt tên URL cho lệnh controller có thể tuân theo một trong các phương pháp sau:
    - Theo các hoạt động Tạo, Đọc, Cập nhật và Xóa (CRUD):
        - Lấy dữ liệu : ***GET***
        - Tạo dữ liệu : ***POST***
        - Cập nhập dữ liệu : ***PUT***
        - Xóa dữ liệu : ***DELETE***
    - Tuân theo các quy ước đặt tên chung dựa trên các hành động:
        - Đinh dạng: ***/{ControllerMapping}/{action}***
        - Ví dụ: /company/add, /company/import, ...
    - Sử dụng chữ thường
    - Sử dụng dấu gạch ngang (-)
- Phải có đường dẫn chung của cả controller rồi mới dẫn tới đường dẫn riêng của từng api

- Tên biến + Tên hàm + Tên package + Tên class
   - Tất cả các loại tên phải tuân thủ theo quy tắc con lạc đà và chữ đầu tiên không viết hoa (TRỪ LÊN CLASS CHỮ ĐẦU VIẾT HOA)
   - Tên đặt phải có ý nghĩa 
   ####Ví dụ:
         - Tên biến : sinhVien
         - Tên hàm: showData()
         - Tên class: HocSinh
         - Tên package: entity, bean, model, service,.....
 
 ### III. Git
 - Tất cả mọi nhánh đều phải tách từ nhánh develop
 - Quy tắc đặt tên nhánh: TaskID/Tên nhánh/ Tên người làm 
    - Ví dụ: SP1-BE/implement-company/HangNT
 - Sau 1 đợt sẽ relase vào nhánh master. Khi có bug gấp phát hiện ra sai từ master sẽ tạo nhánh hot fix và tạo trực tiếp từ master theo format: HOTFIX-BE(hoặc FE)/Tên việc/Tên người
    - Ví dụ: HOTFIX-BE/Fix-bug-UI/HangNT
 - Khi implement xong thì phải tạo MR và add 2 người còn lại vào review. Bug => Fix. 2 người còn lại approve => merge 
 - Rebase commit after push 
- Khi viết UT cover ít nhất 80%
