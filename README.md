# bt1SS1_IT102

1. Phân tích I/O
Input
ma_mon: Mã món ăn (int)
don_gia: Đơn giá (float)
so_luong: Số lượng đặt (int)
khoang_cach: Khoảng cách giao hàng (float)
is_peak: Giờ cao điểm (int)
is_store_open: Trạng thái cửa hàng (int)
ton_kho: Số lượng tồn kho (int)
loai_tai_khoan: VIP/Normal (char)

Output
Tiền món ăn
Phí giao hàng
Giảm Freeship
Phụ phí cao điểm
Trạng thái đơn hàng
Tổng tiền thanh toán

2. Cách xử lý
subtotal = don_gia * so_luong
shipping = khoang_cach * 5000
Freeship khi (subtotal >= 100000 && khoang_cach <= 5) || loai_tai_khoan == 'V'.
Phụ phí cao điểm: 10000 * is_peak.
Đơn hợp lệ khi cửa hàng mở, tồn kho đủ, số lượng > 0 và đơn giá > 0.
Dùng kết quả logic 0/1 để tính toán, không sử dụng if/else, switch hoặc vòng lặp.
Sử dụng scanf(" %c", &loai_tai_khoan) để tránh lỗi bộ đệm khi nhập char.

3. Công thức tổng tiền
final_payable = (subtotal + shipping - freeship_discount + peak_surcharge) * is_valid;

Nếu đơn hàng không hợp lệ (is_valid = 0) thì tổng tiền thanh toán bằng 0 VNĐ.
