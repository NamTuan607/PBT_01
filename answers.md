Câu A1 — HTTP & Browser

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
3. Screenshot tab Network (mô tả)
Sau khi mở một trang web và vào tab Network:  
- Status Code của request đầu tiên:
Nằm ở dòng đầu tiên (thường là request document), cột Status (ví dụ: 200).
- Tổng thời gian load trang:
Hiển thị ở phía dưới tab Network (ví dụ: “Finish: 1.25 s”).
- Một request trả về file CSS:
Một dòng có Type = stylesheet hoặc file có đuôi .css.

Câu A2 — Semantic HTML

1. Tại sao SEO thấp?
Trang web sử dụng quá nhiều thẻ <div> không có ý nghĩa (div soup), khiến:
- Google không hiểu cấu trúc trang
- Không phân biệt được header, nội dung chính, sản phẩm, footer
- Nội dung quan trọng không được ưu tiên (không có heading đúng)
- Thiếu thông tin mô tả (alt, semantic tags)
→ Kết quả: SEO kém
2. Các lỗi semantic (ít nhất 4 lỗi)
 - Lỗi 1: Dùng <div> thay vì <header>, <nav>, <footer>
Không thể hiện rõ cấu trúc trang
 - Lỗi 2: Menu không dùng <nav>
Google không biết đây là phần điều hướng
 - Lỗi 3: Sản phẩm không dùng <article>
Mỗi sản phẩm là nội dung độc lập → nên dùng <article>
 - Lỗi 4: Tiêu đề không dùng heading (<h1>, <h2>)
"iPhone 16 Pro" nên là heading để SEO nhận diện
 - Lỗi 5: Ảnh không có alt
Google không hiểu nội dung ảnh
3. Code đã sửa
  <header>
      <div class="logo">ShopTLU</div>
      <nav>
          <a href="/">Trang chủ</a>
          <a href="/products">Sản phẩm</a>
      </nav>
  </header>
  
  <main>
      <article class="product">
          <h2>iPhone 16 Pro</h2>
          <p class="price">25.990.000đ</p>
          
          <figure>
              <img src="iphone.jpg" alt="iPhone 16 Pro">
          </figure>
      </article>
  </main>
  
  <footer>
      <p>© 2026 ShopTLU</p>
  </footer>
  
Câu A3 — Block vs Inline

1. Kết quả hiển thị (text art)
  Hộp 1
  Text A Text B
  Hộp 2
  Text C Text D
  Hộp 3
2. Giải thích
  <div> là block element
  → chiếm toàn bộ chiều ngang
  → luôn xuống dòng mới
  <span> và <strong> là inline element
  → chỉ chiếm phần nội dung
  → nằm trên cùng một dòng nếu còn chỗ
3. Phân tích từng dòng
  <div>Hộp 1</div>
  → block → chiếm 1 dòng riêng
  <span>Text A</span> + <span>Text B</span>
  → inline → nằm cùng dòng → Text A Text B
  <div>Hộp 2</div>
  → block → xuống dòng
  <span>Text C</span> + <strong>Text D</strong>
  → đều inline → cùng dòng → Text C Text D
  <div>Hộp 3</div>
  → block → dòng mới

Câu A4 — Table
  
1. Sự khác nhau giữa <thead>, <tbody>, <tfoot>
  <thead> (Table Head)
  → Chứa phần tiêu đề của bảng (các cột)
  → Thường dùng với <th>
  → Ví dụ: Tên sản phẩm, Giá, Số lượng
  <tbody> (Table Body)
  → Chứa dữ liệu chính của bảng
  → Bao gồm nhiều dòng <tr> với <td>
  <tfoot> (Table Footer)
  → Chứa phần cuối bảng
  → Thường dùng để hiển thị tổng kết (tổng tiền, thống kê...)
2. Tại sao KHÔNG NÊN dùng table để tạo layout?
   - Lý do 1: Sai mục đích (không semantic)
  Table dùng cho dữ liệu dạng bảng
  Dùng để layout làm Google hiểu sai cấu trúc trang → SEO kém
   - Lý do 2: Khó responsive
  Table khó co giãn trên mobile
  Không linh hoạt như CSS (Flexbox, Grid)
   - Lý do 3: Code phức tạp, khó maintain
  Lồng nhiều <table>, <tr>, <td> → rối code
  Khó sửa, khó debug
