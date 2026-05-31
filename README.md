# Hệ thống Tái Định Danh Người Đa Camera

Khóa luận tốt nghiệp — Đậu Đức Giáp  
Trường ĐH Khoa học Tự nhiên, ĐHQGHN · 2026

---

## Giới thiệu

Hệ thống nhận diện và theo dõi người trên nhiều camera đồng thời. Khi một người di chuyển qua các camera khác nhau, hệ thống tự động duy trì cùng một mã danh tính xuyên suốt.

**Luồng xử lý:**
```
RTSP / Video → GStreamer → YOLO-Pose → ByteTrack → KPR → FAISS → Giao diện web
```

---

## Demo

Video demo: [`demo.mp4`](demo/Screencast%20from%202026-04-09%2007-27-13.mp4)

---

## Kết quả

| Tập dữ liệu | Rank-1 | mAP |
|-------------|:------:|:---:|
| Occluded-DukeMTMC | 80.1% | 68.1% |
| Occ-PoseTrack | 91.8% | 81.2% |

Tốc độ xử lý: ~25 FPS / camera trên GPU RTX 3050 Ti 4GB.

---

## Tham khảo

- KPR: Somers et al., ECCV 2024
- ByteTrack: Zhang et al., ECCV 2022
- YOLO-Pose: Ultralytics v8
