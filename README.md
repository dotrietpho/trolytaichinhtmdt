# Trợ lý tài chính cho nhà bán hàng TMĐT

Website tính **lợi nhuận và giá bán** cho người bán hàng trên sàn thương mại điện tử (**Shopee**, **TikTok Shop**). Sản phẩm thuộc bài nộp học phần **Kinh doanh số**, Trường Đại học Kinh tế TP.HCM (UEH), **Nhóm 2**.

- **Tác giả:** Đỗ Triết Phổ
- **Học phần:** Kinh doanh số, UEH
- **Truy cập website:**
  - GitHub Pages: https://dotrietpho.github.io/trolytaichinhtmdt
  - Netlify: https://trolytaichinhtmdt.netlify.app

## Vấn đề giải quyết

Nhiều người bán chỉ theo dõi doanh thu và số đơn, trong khi lợi nhuận bị bào mòn bởi phí cố định, phí xử lý giao dịch, phí hạ tầng, voucher, vận chuyển, quảng cáo, thuế và đơn hoàn/hủy. Website giúp trả lời nhanh: *mỗi đơn lãi hay lỗ, cần bán bao nhiêu đơn để hòa vốn, quảng cáo tối đa bao nhiêu, bán giá nào thì đạt biên lãi mong muốn, và sàn nào có lợi hơn*.

## Tính năng

- **Lợi nhuận mỗi đơn:** thẻ kết luận Lãi/Lỗ, biên lợi nhuận, bảng phân rã chi phí theo % giá bán, cảnh báo (đơn lỗ, biên mỏng, quảng cáo vượt mức).
- **Gợi ý giá bán:** nhập biên lãi mong muốn, website đề xuất giá (đặt biên 0% để ra giá hòa vốn tối thiểu).
- **Hòa vốn và quảng cáo:** số đơn hòa vốn, doanh thu hòa vốn, CPA tối đa, ROAS hòa vốn và ROAS hiện tại.
- **Kịch bản giá:** so sánh 3 mức giá và số đơn dự kiến, tính lãi ròng theo tháng.
- **Phễu chuyển đổi:** lượt xem, giỏ hàng, đơn hàng, kèm gợi ý điểm nghẽn.
- **So sánh sàn:** Shopee và TikTok Shop cho cùng một sản phẩm.
- **Thông số tùy chỉnh:** nạp mức phí mặc định của Shopee hoặc TikTok Shop, sau đó sửa từng khoản; chế độ sáng/tối tự động; lưu dữ liệu trong trình duyệt; sao chép kết quả; đặt lại.

## Cách sử dụng

1. Mở website, chọn sàn (**Shopee**, **TikTok Shop** hoặc **Tùy chỉnh**).
2. Nhập thông số ở cột trái: giá bán, giá vốn, voucher, phí sàn, thuế, ship, đóng gói, quảng cáo, tỷ lệ hoàn/hủy, chi phí cố định.
3. Xem kết quả ở cột phải và chuyển giữa các tab. Kết quả cập nhật ngay khi nhập.

Quy ước nhập số: `45.000` hiểu là 45000; `0,5` và `0.5` đều hiểu là 0,5.

## Công thức chính

```
d      = Giá bán - Giảm giá shop chịu
Phí sàn = d x phí cố định + (d + ship người mua trả) x phí xử lý giao dịch
          + phí hạ tầng + Voucher Xtra + affiliate
Thuế   = d x (GTGT + TNCN)
Lãi/đơn = d - (giá vốn + phí sàn + ship + đóng gói + quảng cáo + thuế + dự phòng hoàn/hủy)
Biên   = Lãi/đơn / Giá bán
Số đơn hòa vốn = làm tròn lên (Chi phí cố định tháng / Lãi/đơn)
ROAS hòa vốn   = Giá bán / (Lãi/đơn + Chi phí quảng cáo/đơn)
```

Công thức đầy đủ, ví dụ tính và các test case có trong báo cáo đi kèm.

## Lưu ý quan trọng

- Mức phí mặc định (phí cố định/hoa hồng, phí xử lý giao dịch, phí hạ tầng, Voucher Xtra) và chính sách thuế **thay đổi thường xuyên**. Hãy đối chiếu trên **Kênh Người Bán Shopee**, **Seller Center TikTok Shop** và với cơ quan thuế trước khi dùng số liệu để ra quyết định.
- Số liệu mẫu (shop giấy in nhiệt) là **số liệu giả định** để minh họa, không phải số liệu kinh doanh thật.
- Website chỉ mang tính tham khảo, không thay thế tư vấn kế toán hoặc thuế.
- Dữ liệu nhập nằm trong trình duyệt của người dùng (`localStorage`), không gửi về máy chủ.

## Công nghệ

HTML5, CSS3, JavaScript thuần, không dùng thư viện hay máy chủ. Toàn bộ giao diện, CSS và JavaScript nằm trong một tệp `index.html`.

## Cấu trúc thư mục

```
trolytaichinhtmdt/
├── index.html   # toàn bộ website
└── README.md    # tài liệu này
```

## Chạy trên máy và đăng lên mạng

**Chạy trên máy:** tải về và mở `index.html` bằng trình duyệt, không cần cài đặt.

**GitHub Pages:** đưa `index.html` lên repository, vào *Settings*, mục *Pages*, chọn *Deploy from a branch*, nhánh `main`, thư mục `/ (root)`.

**Netlify:** kéo thả thư mục chứa `index.html` vào trang Netlify Drop (app.netlify.com/drop).

## Gian hàng

Tác giả bán giấy in nhiệt (giấy in bill) trên Shopee: https://shopee.vn/mayinnhiet4b
