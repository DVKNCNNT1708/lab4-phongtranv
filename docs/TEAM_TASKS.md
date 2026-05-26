# TEAM_TASKS.md – Việc cần làm theo nhóm

Mỗi nhóm bắt đầu từ repo mẫu này và thay phần IoT bằng service của mình.

---

## Việc chung cho mọi nhóm

- [x] Copy contract từ Lab 03 vào thư mục `contracts/`.
- [x] Đảm bảo service có `GET /health`.
- [x] Viết hoặc cập nhật `Dockerfile` (Đã patch lỗi bằng `sed`).
- [x] Viết `.dockerignore`.
- [x] Viết `.env.example`.
- [x] Viết `RUN_LOCAL.md`.
- [x] Build image (Đã build thành công với `--no-cache`).
- [x] Run container.
- [x] Chạy Postman Collection từ Lab 03 trên container (Pass 100%).
- [x] Xuất Newman report (Đã có trong folder `reports/`).
- [x] Chụp bằng chứng `/health` hoặc log container (Đã lưu trong folder `Evidence/`).
- [x] Ghi tag image đã push (Đã có image tag `fit4110/iot-ingestion:lab04`).

---

## Gợi ý theo service

| Service | Điểm cần chú ý |
|---|---|
| IoT Ingestion | API nhận telemetry, auth token, `/health`, test boundary nhiệt độ |
| Camera Stream | Dùng `opencv-python-headless`, chuẩn bị 1 ảnh mẫu, chưa cần RTSP thật |
| Access Gate | Nếu chưa có DB trong Lab 04, dùng in-memory hoặc DB ngoài; Compose để Buổi 5 |
| AI Vision | Có thể dùng mock model hoặc YOLOv8n nhỏ; kiểm soát dung lượng image |
| Analytics | Nhận event JSON giả; TimescaleDB để Buổi 5 |
| Core Business | Policy evaluation chạy bằng config/env |
| Notification | Channel mock là đủ; không commit Telegram/email token thật |