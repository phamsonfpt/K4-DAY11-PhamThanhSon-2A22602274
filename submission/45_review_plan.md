# Kế hoạch review từ lỗi quan sát được
| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| adasind_060000.jpg | 5 lỗi Spurious của Model | Zone mid sai nghiêm trọng | submission/screenshots/spurious_model.png |
| adasind_102750.jpg | Lỗi Missing từ Annotator | Zone center hay bị sót vật | submission/screenshots/missing_annotator.png |
Giới hạn của kết luận từ ba frame ADASIND: 3 frame là một mẫu quá nhỏ, không thể đại diện cho toàn bộ phân phối lỗi của cả triệu bức ảnh.
## Chuyển sang kế hoạch bốn camera giả lập
Cách soát độ phủ của 200 frame ở 45_sampling_plan.csv (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh như nhiều ca độc lập), và vì sao kế hoạch đã chọn giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: Lấy mẫu cách đều (ví dụ 10 giây/frame) để tránh sự tương đồng giữa các frame liền kề. Điều này giúp tăng tối đa đa dạng không gian mẫu (độ phủ), từ đó tìm ra ca corner-case (khó) dễ dàng hơn, thay vì đo lường thống kê (cần số lượng lớn ngẫu nhiên).
