# 📝 PHẦN A

## Câu A1 --- HTTP & Browser

### 1. Khi nhập `https://shopee.vn` và nhấn Enter

Các bước xảy ra theo thứ tự:

1.  **DNS Lookup**\
    Trình duyệt gửi yêu cầu tới DNS để phân giải tên miền `shopee.vn`
    thành địa chỉ IP.

2.  **Thiết lập kết nối TCP + TLS**\
    Trình duyệt tạo kết nối TCP với server và thực hiện bắt tay TLS để
    mã hóa (HTTPS).

3.  **Gửi HTTP Request**\
    Trình duyệt gửi request (thường là `GET /`) tới server.

4.  **Server xử lý và trả HTTP Response**\
    Server xử lý yêu cầu và trả về nội dung (HTML, dữ liệu...).

5.  **Trình duyệt parse HTML**\
    Trình duyệt đọc HTML và xây dựng DOM.

6.  **Tải thêm tài nguyên (CSS, JS, ảnh...)**\
    Trình duyệt gửi thêm nhiều request để lấy các file cần thiết.

7.  **Render trang web**\
    Parse CSS, chạy JavaScript và hiển thị giao diện hoàn chỉnh lên màn
    hình.

### 2. Tab Network trong Chrome DevTools hiển thị gì?

-   Danh sách request (HTML, CSS, JS, ảnh, API...)
-   Status Code (200, 404, 500...)
-   Thời gian tải
-   Kích thước tài nguyên
-   Loại tài nguyên
-   Timeline (waterfall)

### 3. Screenshot tab Network

-   Status Code: dòng đầu tiên, cột Status\
-   Tổng thời gian: dòng "Finish"\
-   CSS: dòng có Type = stylesheet

------------------------------------------------------------------------

## Câu A2 --- Semantic HTML

### Lý do SEO thấp

-   Dùng quá nhiều `<div>`
-   Không có semantic structure
-   Không có heading
-   Thiếu alt

### Lỗi semantic

-   Không dùng `<header>`, `<nav>`, `<footer>`
-   Menu không dùng `<nav>`
-   Không dùng `<article>`
-   Không có heading
-   Ảnh thiếu alt

------------------------------------------------------------------------

## Câu A3 --- Block vs Inline

    Hộp 1
    Text A Text B
    Hộp 2
    Text C Text D
    Hộp 3

-   `<div>`: block → xuống dòng\
-   `<span>`, `<strong>`: inline → cùng dòng

------------------------------------------------------------------------

## Câu A4 --- Table

-   `<thead>`: tiêu đề\
-   `<tbody>`: nội dung\
-   `<tfoot>`: tổng kết

### Không nên dùng table để layout:

-   Sai mục đích
-   Khó responsive
-   Khó maintain

------------------------------------------------------------------------

# 📝 PHẦN C

## Câu C1 --- HTML Structure
<header> <!-- phần đầu trang -->
    <nav> <!-- điều hướng chính -->
        <ul>
            <li><a href="#">Trang chủ</a></li>
            <li><a href="#">Sản phẩm</a></li>
        </ul>
    </nav>
</header>

<nav aria-label="breadcrumb"> <!-- breadcrumb -->
    <ol>
        <li><a href="#">Trang chủ</a></li>
        <li><a href="#">Điện thoại</a></li>
        <li>iPhone 16</li>
    </ol>
</nav>

<main> <!-- nội dung chính -->

    <section class="product-detail">

        <section class="product-images">
            <figure><img src="#" alt="Ảnh sản phẩm"></figure>
            <figure><img src="#" alt="Ảnh sản phẩm"></figure>
            <figure><img src="#" alt="Ảnh sản phẩm"></figure>
            <figure><img src="#" alt="Ảnh sản phẩm"></figure>
            <figure><img src="#" alt="Ảnh sản phẩm"></figure>
        </section>

        <article class="product-info">
            <h1>Tên sản phẩm</h1>
            <p class="price">Giá</p>
            <p class="rating">Đánh giá sao</p>

            <section class="description">
                <p>Mô tả sản phẩm</p>
            </section>
        </article>

        <section class="specs">
            <h2>Thông số kỹ thuật</h2>
            <table>
                <thead>
                    <tr>
                        <th>Thông số</th>
                        <th>Giá trị</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>...</td>
                        <td>...</td>
                    </tr>
                </tbody>
            </table>
        </section>

        <section class="reviews">
            <h2>Đánh giá</h2>
            <article class="review">
                <p>Nội dung bình luận</p>
            </article>
        </section>

    </section>

    <aside>
        <h2>Sản phẩm tương tự</h2>
        <article class="related-product">
            <p>Tên sản phẩm</p>
        </article>
    </aside>

</main>

<footer>
    <p>© 2026</p>
</footer>
## Câu C2 --- Tranh luận

Semantic HTML giúp SEO tốt hơn và hỗ trợ accessibility.\
Google hiểu cấu trúc trang tốt hơn khi dùng `<header>`, `<main>`,
`<article>`.\
Screen reader cũng hoạt động tốt hơn.

`<div>` vẫn dùng khi cần layout.

## Bài B3 --- Debug HTML

Lỗi 1: Dòng 1 — `<!DOCTYPE>` không đầy đủ chuẩn HTML5 — Sửa thành `<!DOCTYPE html>`.

Lỗi 2: Dòng 2 — Thẻ `<html>` thiếu thuộc tính ngôn ngữ — Sửa thành `<html lang="vi">`.

Lỗi 3: Dòng 4 — Thẻ `<title>` chưa đóng — Thêm `</title>`.

Lỗi 4: Dòng 5 — Khai báo mã hóa `utf8` không đúng chuẩn viết phổ biến — Sửa thành `UTF-8`.

Lỗi 5: Dòng 8 — Thẻ `<h1>` đóng sai (`<h1>` thay vì `</h1>`) — Sửa thành `<h1>Welcome to ShopTLU</h1>`.

Lỗi 6: Dòng 12 — Thẻ `<a>` đầu tiên chưa đóng đúng — Sửa thành `<a href="#home">Trang chủ</a>`.

Lỗi 7: Dòng 13 — Link sản phẩm dùng đường dẫn không rõ ngữ cảnh trong bài mẫu — Sửa thành `<a href="#products">Sản phẩm</a>`.

Lỗi 8: Dòng 20 — Giá trị thuộc tính `src` chưa đặt trong dấu ngoặc kép — Sửa `src=iphone.jpg` thành `src="iphone.jpg"`.

Lỗi 9: Dòng 20 — Ảnh thiếu thuộc tính mô tả thay thế — Thêm `alt="iPhone 16 Pro"` cho thẻ `<img>`.

Lỗi 10: Dòng 22 — Thẻ `<p>` và `<b>` lồng/đóng sai thứ tự (`</p></b>`) — Sửa thành `<p>Giá: <b>25.990.000đ</b></p>`.

Lỗi 11: Dòng 27-36 — Bảng thiếu nhóm cấu trúc ngữ nghĩa — Bổ sung `<thead>` cho dòng tiêu đề và `<tbody>` cho dữ liệu.

Lỗi 12: Dòng 29-30 — Ô tiêu đề bảng đang dùng `<td>` thay vì `<th>` — Sửa hai ô đầu thành `<th>`.

Lỗi 13: Dòng 40 — Tài liệu có 2 thẻ `<main>` (sai semantic, chỉ nên có 1) — Đổi khối thứ hai thành `<aside>`.

Lỗi 14: Dòng 45 — Thẻ `<p>` trong footer chưa đóng — Thêm `</p>`.

Lỗi 15: Cuối tài liệu — Thiếu thẻ đóng `</html>` — Bổ sung `</html>`.

## Bài B4 (15đ) --- Phân tích trang web thật (tiki.vn)

Trang được chọn: `https://tiki.vn`

### 1) Elements: Semantic HTML5

Khi mở DevTools (F12) ở trang chủ tiki.vn và Inspect các vùng chính, có thể xác nhận:

- Thẻ semantic dùng đúng:
    - `<header>`: bao phần đầu trang (logo, ô tìm kiếm, tài khoản, giỏ hàng).
    - `<main>`: bao khối nội dung chính (banner, danh mục, block sản phẩm).
    - `<footer>`: bao phần chân trang (hỗ trợ khách hàng, liên kết, thông tin công ty).

- Thẻ semantic dùng chưa tối ưu (nếu thấy trong DOM runtime của bạn):
    - Khu menu điều hướng chính hiển thị như thanh danh mục nhưng không bọc bằng `<nav>`, chủ yếu là `<div>`.
    - Các khối sản phẩm/lists có thể dùng nhiều `<div>` thay vì `<section>`/`<article>` cho từng cụm nội dung.

Ảnh bạn tự chụp và lưu:
- `screenshots/b4-elements-header-main-footer.png`
- `screenshots/b4-elements-nonsemantic.png`

### 2) Elements: Tìm `<table>`

Trang chủ tiki.vn không có `<table>` trong khung nội dung chính.


### 3) Elements: Tìm `<form>` (ô tìm kiếm)

Trang chủ tiki.vn không có `<form>` trong khung nội dung chính.

<input type="text">

