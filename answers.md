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
