# Kế hoạch Gold Set cho 4 camera
- **front**: Cần test kỹ các ca normal/hard (ngược sáng). Dễ bị mất vật ở xa. Cần 1 QC độc lập.
- **rear**: Bị ánh đèn pha (hard). Calibration quan trọng. Bất đồng giải quyết qua vote 3 người.
- **left**: Fisheye méo nặng. Refresh sau 500 ảnh.
- **right**: Policy cho seam: Nếu vật thể xuất hiện >50% ở camera right thì right ưu tiên vẽ.
