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
  - <thead> (Table Head)
  Chứa phần tiêu đề của bảng (các cột)
  Thường dùng với <th>
  Ví dụ: Tên sản phẩm, Giá, Số lượng
  - <tbody> (Table Body)
  Chứa dữ liệu chính của bảng
  Bao gồm nhiều dòng <tr> với <td>
  - <tfoot> (Table Footer)
  Chứa phần cuối bảng
  Thường dùng để hiển thị tổng kết (tổng tiền, thống kê...)
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

Câu C1 — Thiết kế cấu trúc HTML

<header> <!-- header: phần đầu trang, chứa logo + navigation -->
    <nav> <!-- nav: khu vực điều hướng chính -->
        <ul> <!-- ul: danh sách menu -->
            <li><a href="#">Trang chủ</a></li>
            <li><a href="#">Sản phẩm</a></li>
        </ul>
    </nav>
</header>

<nav aria-label="breadcrumb"> <!-- nav: điều hướng, breadcrumb là dạng navigation -->
    <ol> <!-- ol: breadcrumb có thứ tự cấp bậc -->
        <li><a href="#">Trang chủ</a></li>
        <li><a href="#">Điện thoại</a></li>
        <li>iPhone 16</li>
    </ol>
</nav>

<main> <!-- main: nội dung chính của trang -->

    <section class="product-detail"> <!-- section: nhóm nội dung chi tiết sản phẩm -->

        <section class="product-images"> <!-- section: khu vực ảnh sản phẩm -->
            <figure> <!-- figure: chứa ảnh -->
                <img src="#" alt="Ảnh sản phẩm"> <!-- img + alt: mô tả ảnh -->
            </figure>
            <figure><img src="#" alt="Ảnh sản phẩm"></figure>
            <figure><img src="#" alt="Ảnh sản phẩm"></figure>
            <figure><img src="#" alt="Ảnh sản phẩm"></figure>
            <figure><img src="#" alt="Ảnh sản phẩm"></figure>
        </section>

        <article class="product-info"> <!-- article: thông tin sản phẩm là nội dung độc lập -->
            <h1>Tên sản phẩm</h1> <!-- h1: tiêu đề chính -->
            <p class="price">Giá</p> <!-- p: đoạn văn hiển thị giá -->
            <p class="rating">Đánh giá sao</p> <!-- p: thông tin rating -->
            <section class="description"> <!-- section: mô tả sản phẩm -->
                <p>Mô tả sản phẩm</p>
            </section>
        </article>

        <section class="specs"> <!-- section: nhóm thông số kỹ thuật -->
            <h2>Thông số kỹ thuật</h2>
            <table> <!-- table: dữ liệu dạng bảng -->
                <thead> <!-- thead: tiêu đề bảng -->
                    <tr>
                        <th>Thông số</th>
                        <th>Giá trị</th>
                    </tr>
                </thead>
                <tbody> <!-- tbody: dữ liệu chính -->
                    <tr>
                        <td>...</td>
                        <td>...</td>
                    </tr>
                </tbody>
            </table>
        </section>

        <section class="reviews"> <!-- section: khu vực đánh giá -->
            <h2>Đánh giá</h2>
            <article class="review"> <!-- article: mỗi bình luận độc lập -->
                <p>Nội dung bình luận</p>
            </article>
        </section>

    </section>

    <aside> <!-- aside: nội dung phụ (sidebar) -->
        <h2>Sản phẩm tương tự</h2>
        <article class="related-product"> <!-- article: mỗi sản phẩm độc lập -->
            <p>Tên sản phẩm</p>
        </article>
    </aside>

</main>

<footer> <!-- footer: phần cuối trang -->
    <p>© 2026</p>
</footer>

Câu C2 — So sánh & Tranh luận

Quan điểm “dùng <div> cho mọi thứ” là sai về mặt kỹ thuật và không phù hợp với phát triển web hiện đại.

- Thứ nhất, về SEO: Semantic HTML giúp công cụ tìm kiếm hiểu rõ cấu trúc trang. Ví dụ, khi dùng <header>, <nav>, <main>, <article>, Google có thể xác định đâu là nội dung chính, đâu là menu. Nếu chỉ dùng <div>, toàn bộ trang trở thành “div soup”, khiến việc index kém hiệu quả và giảm thứ hạng tìm kiếm.

- Thứ hai, về Accessibility (khả năng truy cập): Các thẻ semantic hỗ trợ screen reader (trình đọc màn hình). Người khiếm thị có thể dùng <nav> để nhảy nhanh tới menu, hoặc <main> để vào nội dung chính. Nếu dùng <div>, các công cụ hỗ trợ không hiểu được vai trò của từng phần, làm giảm trải nghiệm người dùng.

- Ví dụ cụ thể: Một trang sản phẩm dùng <article> cho mỗi sản phẩm và <h1> cho tên sản phẩm sẽ giúp Google hiểu đây là nội dung chính → dễ lên top hơn so với việc chỉ dùng <div class="product">.

- Tuy nhiên, <div> vẫn cần thiết trong một số trường hợp. Ví dụ: dùng <div> làm container để layout bằng CSS (Flexbox/Grid) hoặc nhóm các phần tử không có ý nghĩa nội dung cụ thể.

Kết luận: Semantic HTML không chỉ giúp SEO tốt hơn mà còn cải thiện accessibility và maintain code. <div> chỉ nên dùng khi không có thẻ semantic phù hợp.
