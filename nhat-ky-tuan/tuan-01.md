# Nhật ký tuần 01 · 05/10 – 11/10/2026

**Lead tuần này:** Lan Nguyễn

**Dữ liệu / task CVAT:**
- Task #42 `2D tuần 1 · Ảnh đường phố` — 12 ảnh, gán khung `car`/`person`/`bicycle` + đa giác `traffic light` (**2D**)
- Task #44 `2D tracking · Video giao lộ` — 120 frame video, gán **track** (**2D tracking**)
- Task #45 `3D tuần 1 · Lidar` — 6 frame point cloud, gán cuboid `car`/`pedestrian` (**3D**)

## Thành viên và phân công

| Thành viên | Vị trí | Phân công tuần này |
|---|---|---|
| Lan Nguyễn | Lead, Reviewer | Chia job, review toàn bộ job, chốt edge case với mentor, viết báo cáo |
| An Trần | Annotator | Job 120, 121 (2D) · 127 (tracking) · 129, 131 (3D) |
| Bình Lê | Annotator | Job 122, 123 (2D) · 126 (tracking) · 130 (3D) |

Job 128 (đoạn cuối video) và job ground truth 134 chưa giao.

## Công việc

| Annotator | Loại | Task | Mã Job | Frame range | Review | Done | Hoàn thành | Ghi chú |
|---|---|---|---:|:---:|---|:---:|:---:|---|
| **An Trần** | 2D | #42 | **120** | 0–2 | Lan Nguyễn | [x] | 🟢 | Đã qua review |
| **An Trần** | 2D | #42 | **121** | 3–5 | Lan Nguyễn | [ ] | 🟡 | Chờ review: 1 issue khung rộng |
| **Bình Lê** | 2D | #42 | **122** | 6–8 | Lan Nguyễn | [ ] | 🔴 | Bị trả lại: 3 issue (1 đã giải quyết) — sửa theo [QĐ-001](../so-quyet-dinh.md#qđ-001) |
| **Bình Lê** | 2D | #42 | **123** | 9–11 | Lan Nguyễn | [ ] | 🔴 | Mới làm 1/3 ảnh, chậm |
| **Bình Lê** | 2D tracking | #44 | **126** | 0–59 | Lan Nguyễn | [ ] | 🔴 | 2 track, chậm — [P-004](../problem-backlog.md#p-004) |
| **An Trần** | 2D tracking | #44 | **127** | 55–114 | Lan Nguyễn | [x] | 🟢 | Đã qua review, 3 track |
| **An Trần** | 3D | #45 | **129** | 0–1 | Lan Nguyễn | [x] | 🟢 | Đã qua review |
| **Bình Lê** | 3D | #45 | **130** | 2–3 | Lan Nguyễn | [ ] | 🟡 | Chờ review: thiếu cuboid xe đỗ |
| **An Trần** | 3D | #45 | **131** | 4–5 | Lan Nguyễn | [ ] | 🔴 | Bị trả lại: cuboid người quá cao — sửa theo [QĐ-002](../so-quyet-dinh.md#qđ-002) |

🔴 0–50% · 🟡 >50–<100% · 🟢 100% · ⬜ chưa bắt đầu

## Tổng kết

- Job xong và đã duyệt: 3 / 9 (120, 127, 129)
- 2D: 1/4 job xong · 2D tracking: 1/2 · 3D: 1/3
- Bị trả lại: 2 job (122, 131) — đều do guideline mơ hồ, đã chốt QĐ-001, QĐ-002
- Edge case mới: P-001, P-002 (đã chốt), P-003 (đang hỏi BTC), P-004 (pain point công cụ)

## Vướng mắc

- [P-001](../problem-backlog.md#p-001) — Người bị che 50–70% → ✅ [QĐ-001](../so-quyet-dinh.md#qđ-001): che dưới 70% vẫn gán + `occluded`
- [P-002](../problem-backlog.md#p-002) — Cuboid người khi point cloud thưa → ✅ [QĐ-002](../so-quyet-dinh.md#qđ-002): cao 1.6–1.8 m
- [P-003](../problem-backlog.md#p-003) — Xe máy ngoài label set → ↗️ đang hỏi BTC
- [P-004](../problem-backlog.md#p-004) — Tracking video chậm → 🔴 mở, cân nhắc làm tool

## Kế hoạch tuần 2

- Bình sửa job 122, An sửa job 131 theo QĐ-001, QĐ-002 rồi nộp duyệt lại đầu tuần.
- Giao job 128 (đoạn cuối video) cho Bình; giao job 125 (2D tuần 2) khi job 123 xong.
- Bắt đầu task 2D tuần 2 (#43) và 3D tuần 2 (#46).
