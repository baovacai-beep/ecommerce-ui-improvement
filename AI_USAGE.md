# NHẬT KÝ SỬ DỤNG CÔNG CỤ AI (AI USAGE LOG)
### Bài tập cá nhân Buổi 2: HTML5 & CSS3 - Sinh viên: Hồ Gia Bảo

| STT | Thời gian | Mục đích sử dụng | Câu lệnh Prompt gửi AI | Kết quả AI phản hồi | Đánh giá & Điều chỉnh độc lập của sinh viên |
| :---: | :---: | :--- | :--- | :--- | :--- |
| 1 | 28/10/2026 | Phân tích mã nguồn Buổi 1 | "Phân tích giao diện danh sách sản phẩm Buổi 1, chỉ ra 3 vấn đề về bố cục, màu sắc và đề xuất hướng cải thiện bằng HTML5/CSS3." | AI chỉ ra lỗi thiếu thẻ ngữ nghĩa, các thẻ bị dính sát nhau, ảnh không đồng đều kích thước. | Chấp nhận phân tích của AI và lập bảng định hướng cải tiến ở Bước 1. |
| 2 | 28/10/2026 | Củng cố HTML5 ngữ nghĩa | "Kiểm tra đoạn mã HTML gồm header, nav, main, section, article xem đã hợp lý và đạt chuẩn W3C chưa." | AI đề xuất bọc thẻ danh mục trong `<nav>`, mỗi sản phẩm đóng gói trong `<article>`. | Áp dụng vào `index.html`, bổ sung đầy đủ thuộc tính `alt` và `loading="lazy"`. |
| 3 | 29/10/2026 | Dàn trang CSS Grid | "Hướng dẫn sử dụng CSS Grid cho danh sách sản phẩm với grid-template-columns, gap và object-fit." | AI gợi ý dùng `grid-template-columns: repeat(auto-fit, minmax(200px, 1fr))` và gán cứng chiều cao ảnh 250px. | **Từ chối chiều cao cứng 250px** vì làm méo ảnh. Đổi sang `aspect-ratio: 1/1` và `object-fit: cover`. |
| 4 | 29/10/2026 | Xử lý lỗi tràn viền Mobile | "Giao diện bị tràn ngang ở màn hình 390px do menu dính một hàng, đề xuất cách sửa ít thay đổi nhất." | AI gợi ý đặt `overflow: hidden` trên toàn trang. | **Từ chối giải pháp che giấu lỗi**. Tự viết Media Query rớt dòng `flex-wrap: wrap` cho Header. |