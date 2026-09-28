# Rework delta

| zone | matched before | matched after | missing before | missing after | spurious before | spurious after |
|---|---:|---:|---:|---:|---:|---:|
| center | 5 | 8 | 4 | 1 | 1 | 0 |
| mid | 8 | 8 | 0 | 0 | 0 | 0 |
| edge | 2 | 3 | 1 | 0 | 0 | 0 |

## Findings action=rework
- adasind_060000.jpg R7 MISSING: Ä‘Ã£ sá»­a
- adasind_060000.jpg R8 MISSING: Ä‘Ã£ sá»­a
- adasind_060000.jpg R9 MISSING: Ä‘Ã£ sá»­a
- adasind_102750.jpg L4 SPURIOUS: Ä‘Ã£ sá»­a
- adasind_102750.jpg R4 MISSING: Ä‘Ã£ sá»­a
- adasind_102750.jpg R5 MISSING: chÆ°a sá»­a
- adasind_060000.jpg R7+M6 MISSING: Ä‘Ã£ sá»­a
- adasind_102750.jpg L4 SPURIOUS: Ä‘Ã£ sá»­a
- adasind_102750.jpg R5+M8 MISSING: chÆ°a sá»­a

## Giải thích nguyên nhân (cho các ca chưa sửa hoặc sửa không thành công)
- **adasind_102750.jpg R5 MISSING**: Box này nằm lọt thỏm trong vùng rìa, kích thước quá hẹp và gần như vô hình do méo fisheye, việc thêm box thủ công vào bị tool gạt vì độ che khuất hoặc IoU không đạt ngưỡng. Quyết định: Giữ nguyên (chấp nhận bỏ sót) để không làm nhiễu dữ liệu.
