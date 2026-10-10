# Problem backlog

## Danh sách

| Mã | Tóm tắt | Loại | 2D/3D | Mục guideline | Trạng thái | Kết quả |
|---|---|---|---|---|---|---|
| [P-001](#p-001) | Người bị che 50–70% có gán `person` không? | Guideline mơ hồ | 2D | §3.2 | ✅ Đã chốt | [QĐ-001](so-quyet-dinh.md#qđ-001) |
| [P-002](#p-002) | Cuboid `pedestrian` khi point cloud quá thưa | Guideline chưa nói tới | 3D | §5.1 | ✅ Đã chốt | [QĐ-002](so-quyet-dinh.md#qđ-002) |
| [P-003](#p-003) | Xe máy gán `bicycle` hay bỏ qua? | Guideline chưa nói tới | 2D | §3.1 | ↗️ Hỏi BTC |  |
| [P-004](#p-004) | Kéo track video chậm, lệch khung khi xe rẽ | Pain point công cụ | 2D tracking | §6 | 🔴 Mở |  |

**Loại**

| Loại | Nghĩa là |
|---|---|
| Guideline chưa nói tới | Tình huống không có trong guideline |
| Guideline mơ hồ | Đọc guideline ra được hai cách hiểu trở lên |
| Guideline mâu thuẫn | Hai mục trong guideline nói ngược nhau |
| Pain point công cụ | Guideline rõ, nhưng làm trên CVAT chậm hoặc dễ sai |

**Trạng thái:** 🔴 Mở · 🗣️ Đang bàn · ↗️ Hỏi BTC · ✅ Đã chốt (trỏ sang QĐ) · 🛠️ Làm tool (trỏ sang `source-tool/`) · ⚪ Bỏ (ghi lý do)

---

## P-001

**Người bị che khoảng 50–70% có phải gán `person` không?**

- **Loại:** Guideline mơ hồ
- **Loại công việc:** 2D
- **Mục guideline:** §3.2
- **Người phát hiện:** Bình Lê 06/10/2026
- **Link CVAT:** http://localhost:8080/tasks/42/jobs/122?frame=6
- **Mô tả:** Guideline nói "đối tượng bị che quá nhiều thì bỏ qua" nhưng không ghi ngưỡng. Reviewer trả job vì thiếu một người bị cột đèn che khoảng 50%.
- **Các cách hiểu:**
  1. Che từ 50% trở lên thì bỏ qua.
  2. Chỉ bỏ qua khi che trên 70%; còn lại vẫn gán và đánh dấu `occluded`.
- **Xử lý tạm trong lúc chờ:** Vẫn gán `person`, bật `occluded`.
- **Kết quả:** ✅ [QĐ-001](so-quyet-dinh.md#qđ-001)

## P-002

**Cuboid `pedestrian` khi point cloud quá thưa: lấy chiều cao bao nhiêu?**

- **Loại:** Guideline chưa nói tới
- **Loại công việc:** 3D
- **Mục guideline:** §5.1
- **Người phát hiện:** An Trần 07/10/2026
- **Link CVAT:** http://localhost:8080/tasks/45/jobs/131?frame=5
- **Mô tả:** Người đi bộ ở xa chỉ có vài chục điểm, cuboid kéo theo điểm cao nhất ra 2.4 m, reviewer trả lại vì quá cao so với người thật.
- **Các cách hiểu:**
  1. Bám đúng các điểm nhìn thấy, kể cả khi ra kích thước vô lý.
  2. Dùng chiều cao chuẩn khoảng 1.6–1.8 m khi điểm quá thưa, vẫn bám tâm theo điểm.
- **Xử lý tạm trong lúc chờ:** Dùng 1.7 m, ghi chú trong issue của job.
- **Kết quả:** ✅ [QĐ-002](so-quyet-dinh.md#qđ-002)

## P-003

**Xe máy gán `bicycle` hay bỏ qua? (label set không có `motorbike`)**

- **Loại:** Guideline chưa nói tới
- **Loại công việc:** 2D
- **Mục guideline:** §3.1
- **Người phát hiện:** Lan Nguyễn 08/10/2026 (khi review)
- **Link CVAT:** http://localhost:8080/tasks/42/jobs/122?frame=8
- **Mô tả:** Label set chỉ có `car`, `person`, `bicycle`, `traffic light`. Ảnh đường phố có nhiều xe máy; annotator gán `bicycle`, reviewer không chắc có đúng không.
- **Các cách hiểu:**
  1. Gán `bicycle` cho mọi xe hai bánh.
  2. Không gán xe máy (ngoài label set), chỉ gán người lái là `person`.
- **Xử lý tạm trong lúc chờ:** Không gán xe máy, chỉ gán người lái.
- **Kết quả:** ↗️ Đã hỏi BTC, chờ trả lời

## P-004

**Kéo track qua nhiều frame video rất chậm, hay lệch khung khi xe đổi hướng**

- **Loại:** Pain point công cụ
- **Loại công việc:** 2D (tracking video)
- **Mục guideline:** §6
- **Người phát hiện:** Bình Lê 10/10/2026
- **Link CVAT:** http://localhost:8080/tasks/44/jobs/126?frame=30
- **Mô tả:** Mỗi track phải đặt keyframe gần như mỗi 5 frame vì nội suy tuyến tính lệch khi xe rẽ; job 60 frame mất khoảng 2 giờ.
- **Xử lý tạm trong lúc chờ:** Đặt keyframe ở frame xe bắt đầu và kết thúc rẽ trước, sau đó mới thêm keyframe giữa.
- **Kết quả:** 🔴 Mở — nếu tuần 2 vẫn chậm sẽ làm tool trong `source-tool/`
