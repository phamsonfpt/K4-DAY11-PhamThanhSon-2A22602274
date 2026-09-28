# Parking Observations

- **Hai vạch đã chọn ở đâu:** Hai vạch parking_line được chọn nằm ở phía bên trái và bên phải của khoang đỗ xe chính giữa góc nhìn, xác định ranh giới cho vị trí đỗ xe.
- **Một dấu sơn/biên đã loại và lý do:** Đã loại bỏ các nét đứt của vạch sơn bị đè lên bởi bánh xe/cản xe đang đỗ, và bóng đổ (shadow) của gờ vỉa hè. Lý do: Theo quy tắc SVM, không được phép nội suy vẽ xuyên qua vùng vật thể che khuất (occluded) và không được gán nhãn bóng đổ như gờ vật lý.
- **Vùng trống (free space) dừng ở đâu:** Đa giác free_space dừng chính xác tại mép gờ bó vỉa (curb) phía trước và ôm sát viền cản của các xe đang đỗ xung quanh, không mở rộng vào vùng không nhìn thấy.
- **Ca còn nghi ngờ:** Các vạch sơn ở sát mép viền (edge zone) của thấu kính mắt cá bị cong và biến dạng mạnh, cộng thêm tình trạng chói sáng ở rìa khiến việc bám đường cong gặp chút khó khăn và có thể sai số nhỏ.
