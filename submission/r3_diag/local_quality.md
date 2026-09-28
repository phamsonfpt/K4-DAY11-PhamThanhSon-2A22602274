# Đối chiếu chất lượng cục bộ — rectangle

Teaching reference, không phải gold set đã phê duyệt; không có điểm đạt tự động.
Nguồn: export r1_craft đã khóa SHA256 `f08bad0867a781b8139562452eb9751081544527450160a99d8ee229c1a55265`; slice `B2-mid`.
Ghép hình học greedy một-một theo IoU ≥ 0.50, rồi so class; H ≥ 40 px.
Box trái nằm chủ yếu trong ignore_region reference không tính. Polygon, polyline, track không được chấm.
Đây là phép tính offline của lab, không phải báo cáo hay kết quả tương đương CVAT Premium.

Frame được tính: adasind_060000.jpg, adasind_086220.jpg, adasind_102750.jpg. Frame thiếu trong export: không.
TP=15; FP=1; FN=5; số lần đối chiếu=21; mean IoU của TP=0.876.

| Chỉ số | Micro | Macro | Nhãn thấp nhất |
|---|---:|---:|---:|
| accuracy | 0.714 | 0.929 | 0.810 |
| precision | 0.938 | 0.964 | 0.857 |
| recall | 0.750 | 0.771 | 0.667 |
| jaccard | 0.714 | 0.754 | 0.600 |
| dice | 0.833 | 0.852 | 0.750 |

| Nhãn | TP | FP | FN | Accuracy | Precision | Recall | Jaccard | Dice |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Bike | 4 | 0 | 0 | 1.000 | 1.000 | 1.000 | 1.000 | 1.000 |
| Pedestrian | 3 | 0 | 1 | 0.952 | 1.000 | 0.750 | 0.750 | 0.857 |
| ThreeWheeler | 6 | 1 | 3 | 0.810 | 0.857 | 0.667 | 0.600 | 0.750 |
| Truck | 2 | 0 | 1 | 0.952 | 1.000 | 0.667 | 0.667 | 0.800 |

| Frame | TP | FP | FN | Accuracy | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| adasind_060000.jpg | 7 | 0 | 3 | 0.700 | 1.000 | 0.700 |
| adasind_086220.jpg | 5 | 0 | 0 | 1.000 | 1.000 | 1.000 |
| adasind_102750.jpg | 3 | 1 | 2 | 0.500 | 0.750 | 0.600 |

Confusion matrix: hàng = teaching reference; cột = export đã khóa.
`<missing>` là thiếu box; `<extra>` là box thừa. Xem `local_quality_confusion.csv`.

| Reference \ Export | Bike | Pedestrian | ThreeWheeler | Truck | <missing> |
|---|---:|---:|---:|---:|---:|
| Bike | 4 | 0 | 0 | 0 | 0 |
| Pedestrian | 0 | 3 | 0 | 0 | 1 |
| ThreeWheeler | 0 | 0 | 6 | 0 | 3 |
| Truck | 0 | 0 | 0 | 2 | 1 |
| <extra> | 0 | 0 | 1 | 0 | 0 |

Chi tiết xung đột trong `local_quality_conflicts.csv`; dữ liệu máy đọc trong `local_quality.json`.
Mismatching label đóng góp một FP cho class vẽ và một FN cho class reference; attribute khác được báo riêng.
Micro accuracy đếm mỗi cặp ghép sai class là một lần đối chiếu; Jaccard đếm cả FP và FN.
Macro/worst bỏ nhãn không xuất hiện ở cả hai phía; chỉ số không có mẫu là N/A.
