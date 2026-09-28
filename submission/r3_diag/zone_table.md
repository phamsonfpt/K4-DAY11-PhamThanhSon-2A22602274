# Zone table (slice của bạn)

Lệnh `python3 lab11.py model` tự ghi bảng số (cùng cách đếm với `r1_craft/compare.md` và `model_compare.md`); chạy lại lệnh sẽ cập nhật bảng và giữ nguyên phần nhận xét. Bạn chỉ viết mục Nhận xét.

| Zone | n_ref | L missing | L spurious | M missing (`LR_noM` + `R_only`) | M thừa (`LM_noR` + `M_only`) | Lỗi L chính (`what`) |
|---|---:|---:|---:|---:|---:|---|
| center | 9 | 4 | 1 | 5 | 8 | MISSING (4) |
| mid | 8 | 0 | 0 | 4 | 10 | — |
| edge | 3 | 1 | 0 | 2 | 0 | MISSING (1) |

## Nhận xét

- Zone nào người (L) và model (M) gây nhiều nhất, dẫn số ở bảng trên: Zone `center` có L missing nhiều nhất (4 lỗi). Model (M) đặc biệt tạo ra cực kỳ nhiều lỗi thừa (M thừa) ở zone `mid` (10 lỗi) và `center` (8 lỗi). Model cũng miss khá nhiều ở `center` (5 lỗi).
- Giả thuyết vì sao (méo fisheye, box lồng, thiếu `ego_body`, ...) và giới hạn của slice ba frame: Model YOLO26m đóng băng dường như không xử lý tốt hiện tượng méo fisheye hoặc bị nhầm lẫn bởi các vật thể chồng chéo ở vùng mid/center, dẫn đến dự đoán thừa (Spurious) quá nhiều. Annotator (L) bỏ sót (Missing) ở vùng center có thể do vật thể quá nhỏ hoặc khó nhìn. Tuy nhiên, tập dữ liệu slice này chỉ có 3 frame, quá ít mẫu để có thể suy rộng thành quy luật chung hay đánh giá toàn diện chất lượng của cả hệ thống model.
