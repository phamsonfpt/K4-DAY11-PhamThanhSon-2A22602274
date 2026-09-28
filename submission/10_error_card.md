# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B2 | BOX_GEOMETRY | 1 |
| center | B2 | MISSING | 11 |
| center | B2 | SPURIOUS | 10 |
| center | C0 | BOX_GEOMETRY | 1 |
| center | C0 | SPURIOUS | 1 |
| edge | B2 | BOX_GEOMETRY | 1 |
| edge | B2 | MISSING | 3 |
| mid | B2 | BOX_GEOMETRY | 1 |
| mid | B2 | MISSING | 4 |
| mid | B2 | SPURIOUS | 10 |
| unknown | C0 | IGNORE_SCOPE | 1 |

## Top defects
- SPURIOUS: 21 (ví dụ frame adasind_019560.jpg)
- MISSING: 18 (ví dụ frame adasind_060000.jpg)
- BOX_GEOMETRY: 4 (ví dụ frame adasind_019560.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (why) và vì sao bạn nghĩ vậy: E4_model_domain. Model YOLO26m không được train với ảnh góc rộng fisheye nên liên tục nhận diện sai (Spurious) ở khu vực center/mid.
- Cách sửa và ai nhận việc (owner): ai_team cần retrain model với dataset fisheye augmentation.
- Bằng chứng: frame adasind_060000.jpg (ảnh submission/screenshots/spurious_model.png), model sinh ra tới 5 box SPURIOUS.
