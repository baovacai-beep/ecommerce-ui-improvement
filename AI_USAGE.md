# AI Usage Log

## 1. Công cụ AI
- **Tên công cụ:** Google Gemini / ChatGPT[cite: 1130]

## 2. Mục đích sử dụng
- Hỗ trợ lập bảng phân tích nghiệp vụ và trải nghiệm người dùng (UI/UX) cho 5 khu vực trên website thương mại điện tử Tiki.vn[cite: 1124, 1130].
- Đề xuất phương án thiết kế giao diện thẻ sản phẩm cải tiến và khung mã nguồn HTML5/CSS3 chuẩn Responsive[cite: 1126, 1127].
- Hỗ trợ rà soát các cú pháp CSS hiện đại (Flexbox, Grid) và tối ưu hóa khả năng tiếp cận (Accessibility)[cite: 1127, 1130].

## 3. Prompt đã sử dụng

### Prompt 1 – Khảo sát và phân tích website
> "Bạn là chuyên gia phân tích nghiệp vụ và thiết kế trải nghiệm người dùng cho website thương mại điện tử[cite: 1124]. Tôi đang khảo sát website: Tiki (https://tiki.vn/)[cite: 1124]. Hãy giúp tôi lập bảng phân tích các khu vực: 1. Trang chủ, 2. Danh mục sản phẩm, 3. Chi tiết sản phẩm, 4. Tìm kiếm, 5. Giỏ hàng[cite: 1125]. Với mỗi khu vực, hãy nêu: Mục đích của chức năng, Thành phần giao diện cần có, Điểm thuận tiện đối với khách hàng, Một vấn đề có thể phát sinh, Một đề xuất cải tiến[cite: 1125]. Không khẳng định những tính năng chưa được kiểm chứng[cite: 1125]. Phân biệt rõ nhận xét dựa trên quan sát và đề xuất của AI[cite: 1125]."

### Prompt 2 – Đề xuất phương án thiết kế giao diện cải tiến
> "Tôi đang thực hiện bài tập phát triển giao diện website thương mại điện tử bằng HTML5 và CSS3[cite: 1126]. Tôi muốn cải tiến khu vực: Lưới danh sách thẻ sản phẩm (Product Card) hiển thị rõ giá gốc, giá khuyến mãi, tỷ lệ giảm giá và nút mua hàng[cite: 1126]. Đối tượng sử dụng: khách hàng mua sắm trực tuyến tại Việt Nam[cite: 1126]. Hãy đề xuất: 1. Bố cục giao diện, 2. Các thành phần HTML cần sử dụng, 3. Cách tổ chức CSS, 4. Cách hiển thị trên máy tính và điện thoại, 5. Những điểm cần kiểm tra về khả năng sử dụng[cite: 1126, 1127]. Trước tiên, hãy giải thích phương án thiết kế[cite: 1127]. Chưa tạo toàn bộ mã nguồn cho đến khi tôi yêu cầu[cite: 1127]."

### Prompt 3 – Sinh mã nguồn HTML/CSS mẫu
> "Dựa trên phương án đã thống nhất, hãy tạo một trang giao diện thương mại điện tử bằng HTML5 và CSS3[cite: 1127]. Yêu cầu: Giao diện có tiêu đề và khu vực sản phẩm; Có tối thiểu 4 sản phẩm mẫu; Mỗi sản phẩm có hình ảnh, tên, giá và nút thao tác; Bố cục phù hợp với màn hình máy tính và điện thoại; Mã HTML có cấu trúc rõ ràng; CSS được tách thành file riêng; Không sử dụng backend hoặc cơ sở dữ liệu; Không đưa thư viện hoặc thành phần không cần thiết vào dự án[cite: 1127]. Giải thích cách chạy trang web và những phần tôi cần kiểm tra[cite: 1127]."

## 4. Kết quả AI đề xuất
- AI cung cấp bảng phân tích chi tiết cấu trúc chức năng của 5 khu vực cốt lõi trên sàn TMĐT[cite: 1124, 1125].
- Đề xuất mô hình phối hợp giữa CSS Grid (cho toàn bộ lưới sản phẩm) và Flexbox (cho việc sắp xếp dọc các phần tử bên trong từng thẻ card)[cite: 1126, 1127].
- Sinh bộ mã nguồn khung cơ bản với màu sắc giả định và các liên kết ảnh placeholder từ internet[cite: 1127].

## 5. Kiểm tra và điều chỉnh
- **Đối chiếu thực tế:** Loại bỏ nhận định của AI cho rằng trên thẻ sản phẩm trang danh mục của Tiki có nút "Xem nhanh (Quick View)" và nút "So sánh", vì qua kiểm tra thực tế trên `tiki.vn`, thẻ sản phẩm là một liên kết duy nhất dẫn thẳng vào trang chi tiết[cite: 1125].
- **Chỉnh sửa kỹ thuật:**
  - Thay thế link ảnh placeholder từ web ngoài bằng 4 file ảnh nội bộ nằm trong thư mục `images/` (`product-demo.jpg`, `Phimgo.jpg`, `docsach.jpg`, `chuot.jpg`) để website hoạt động ổn định không phụ thuộc internet[cite: 1127, 1128].
  - Sửa lỗi lệch hàng: Ban đầu khi tiêu đề sản phẩm dài ngắn khác nhau, khung giá bị đẩy lên xuống lộn xộn. Đã tự bổ sung thuộc tính `-webkit-line-clamp: 2` kết hợp `min-height: 2.9rem` cho tiêu đề và `margin-top: auto;` cho cụm giá để chân thẻ luôn thẳng tắp.
  - Khắc phục lỗi hiển thị Mobile: Sử dụng Chrome DevTools giả lập màn hình `375px`, nhận thấy thanh tìm kiếm ở Header bị ép dẹt, đã bổ sung `flex-wrap: wrap` cho `.header-inner` để thanh tìm kiếm tự động xuống dòng và hiển thị vừa vặn 100% chiều ngang[cite: 1103, 1128].

## 6. Phần tôi hiểu và có thể giải thích
- **Cấu trúc HTML5 Semantics:** Hiểu và giải thích được lý do chọn dùng thẻ `<article>` cho thẻ sản phẩm (thể hiện tính độc lập của một mặt hàng), `<del>` cho giá cũ bị gạch bỏ và `<section>` cho phân vùng danh mục[cite: 1127].
- **Bố cục CSS Grid:** Hiểu cách hoạt động của `display: grid; grid-template-columns: repeat(4, 1fr); gap: 20px;` giúp chia 4 cột bằng nhau và tự động co giãn theo khung nhìn.
- **Kỹ thuật Flexbox căn chỉnh chân:** Giải thích được cơ chế hoạt động của `margin-top: auto;` bên trong flex container để tự động hấp thụ khoảng trống thừa, giữ các nút bấm luôn thẳng hàng.
- **Responsive Design:** Giải thích được nguyên lý chuyển đổi breakpoint `@media (max-width: 992px)` (2 cột) và `@media (max-width: 576px)` (1 cột) để tối ưu cho người dùng điện thoại[cite: 1127].