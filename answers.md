Ca
1. Khi nhập https://shopee.vn và nhấn Enter

Các bước xảy ra theo thứ tự:

  1. DNS Lookup
Trình duyệt gửi yêu cầu tới DNS để phân giải tên miền shopee.vn thành địa chỉ IP.
  2. Thiết lập kết nối TCP + TLS
Trình duyệt tạo kết nối TCP với server và thực hiện bắt tay TLS để mã hóa (HTTPS).
  3. Gửi HTTP Request
Trình duyệt gửi request (thường là GET /) tới server.
  4. Server xử lý và trả HTTP Response
Server xử lý yêu cầu và trả về nội dung (HTML, dữ liệu...).
  5. Trình duyệt parse HTML
Trình duyệt đọc HTML và xây dựng DOM.
  6. Tải thêm tài nguyên (CSS, JS, ảnh...)
Trình duyệt gửi thêm nhiều request để lấy các file cần thiết.
  7. Render trang web
Parse CSS, chạy JavaScript và hiển thị giao diện hoàn chỉnh lên màn hình.

2. Tab Network trong Chrome DevTools hiển thị gì?

Tab Network hiển thị:

- Danh sách tất cả các request của trang web (HTML, CSS, JS, ảnh, API...)
- Status Code của từng request (200, 404, 500...)
- Thời gian tải (load time)
- Kích thước tài nguyên
- Loại tài nguyên (document, stylesheet, script...)
- Biểu đồ timeline (waterfall) thể hiện quá trình tải
- 
3. Screenshot tab Network (mô tả)

Sau khi mở một trang web và vào tab Network:  
- Status Code của request đầu tiên:
Nằm ở dòng đầu tiên (thường là request document), cột Status (ví dụ: 200).
- Tổng thời gian load trang:
Hiển thị ở phía dưới tab Network (ví dụ: “Finish: 1.25 s”).
- Một request trả về file CSS:
Một dòng có Type = stylesheet hoặc file có đuôi .css.
