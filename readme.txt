=== BizMatch Quick Buy - Mua Hàng Nhanh ===
Contributors: ngocnguyen
Tags: woocommerce, quick buy, mua hàng nhanh, popup, buy now
Requires at least: 5.0
Tested up to: 7.1
WC requires at least: 3.5.4
WC tested up to: 8.0
Requires PHP: 7.2
Stable tag: 1.0.1
License: GPLv2 or later
License URI: https://www.gnu.org/licenses/gpl-2.0.html

Plugin "Mua hàng nhanh" cho WooCommerce: hiển thị popup đặt hàng ngay trên trang sản phẩm, không cần vào giỏ hàng / trang thanh toán.

== Mô tả ==

BizMatch Quick Buy giúp khách hàng đặt mua sản phẩm chỉ với vài thao tác, ngay tại trang chi tiết sản phẩm, dưới dạng popup — không cần đi qua giỏ hàng hay trang thanh toán mặc định của WooCommerce.

**Tính năng chính**

* Nút "Mua ngay" hiển thị ngay trên trang chi tiết sản phẩm (tự động thêm sau nút "Thêm vào giỏ hàng").
* Form đặt hàng dạng popup: họ tên, số điện thoại, email (tuỳ chọn), địa chỉ, ghi chú...
* Hỗ trợ chọn Tỉnh/Thành - Quận/Huyện - Xã/Phường (dữ liệu hành chính Việt Nam), tính phí vận chuyển theo khu vực.
* Áp dụng mã giảm giá (coupon) ngay trong popup.
* Hỗ trợ đơn giản (simple product) và sản phẩm có thuộc tính (variable product).
* Tự động điền thông tin nếu khách đã đăng nhập.
* Có thể hiển thị nút mua nhanh ngay trong danh sách sản phẩm (shop loop).
* Shortcode để chèn nút / form mua nhanh ở bất kỳ đâu.
* Tuỳ biến được tiêu đề popup, nội dung thông báo thành công/thất bại, văn bản nút bấm...
* Đa ngôn ngữ (kèm sẵn bản dịch Tiếng Việt).

**Shortcode**

Hiển thị nút mua nhanh:

    [bizmatch_quickbuy id="ID_SAN_PHAM" button_text1="Mua ngay" button_text2="Gọi xác nhận và giao hàng tận nơi" small_link="0"]

* `id` (bắt buộc): ID sản phẩm.
* `button_text1`, `button_text2`: tuỳ chỉnh chữ hiển thị trên nút.
* `small_link`: `1` để hiển thị dạng link chữ đơn giản, `0` (mặc định) để hiển thị dạng nút có style sẵn.
* `view`: `0` để chỉ hiển thị nút mà không kèm popup (dùng khi popup đã được render riêng, ví dụ trong trang chi tiết sản phẩm).

Hiển thị nguyên form mua nhanh (không cần nút bấm):

    [bizmatch_quickbuy_form id="ID_SAN_PHAM"]

**Di chuyển / ẩn nút mua ngay mặc định**

Di chuyển nút ra sau nút "Thêm vào giỏ hàng" (thêm vào functions.php):

    global $bizmatch_quickbuy;
    remove_action('woocommerce_single_product_summary', array($bizmatch_quickbuy, 'add_button_quick_buy'), 35);
    add_action('woocommerce_after_add_to_cart_button', array($bizmatch_quickbuy, 'add_button_quick_buy'), 35);

Ẩn hẳn nút mua ngay mặc định:

    global $bizmatch_quickbuy;
    remove_action('woocommerce_single_product_summary', array($bizmatch_quickbuy, 'add_button_quick_buy'), 35);

== Cài đặt ==

1. Upload thư mục `bizmatch-quick-buy` vào `/wp-content/plugins/`, hoặc cài trực tiếp file .zip qua trang Plugins của WordPress.
2. Kích hoạt plugin qua menu 'Plugins' trong WordPress (yêu cầu đã cài và kích hoạt WooCommerce).
3. Vào **Settings → Quick Buy Setting** để cấu hình.

== Changelog ==

= 1.0.1 =
* Sửa lỗi: không còn tự động in sẵn (ẩn) toàn bộ form/biến thể sản phẩm trên mọi trang sản phẩm. Nội dung popup giờ chỉ được tải qua AJAX đúng lúc bấm nút "Mua ngay", tránh xung đột với các script tạo swatch/biến thể tùy chỉnh khác của theme (gây hiện tượng lặp bộ chọn biến thể trên trang).

= 1.0.0 =
* Phiên bản đầu tiên của BizMatch Quick Buy.
