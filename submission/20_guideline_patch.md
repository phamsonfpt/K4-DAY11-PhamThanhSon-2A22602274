# Guideline patch
- **Rule mới đề xuất:** Định nghĩa quy chuẩn hiển thị tối thiểu (VD: kích thước > 10px hoặc nhìn rõ hình khối) trước khi bắt buộc vẽ box cho vật thể ở mép. Dưới ngưỡng thì bỏ qua.
- **Áp dụng cho:** Toàn bộ class (Bike, Truck, Pedestrian...) nằm ở vùng edge/bị che khuất nặng.
- **Vì sao luật hiện tại (docs/02-rules-vi.md) không đủ:** Thiếu ranh giới cụ thể giữa vật thể cần vẽ và vật thể 'vô hình'. Dẫn đến tranh cãi giữa Annotator và QC/Reference (như ca R5 ở adasind_102750.jpg).
- **
ules_version mới:** v1.1.0
- **Hiệu lực từ:** r4 (pha QA tiếp theo)
