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
| **An Trần** | 2D | #42 | **121** | 3–5 | Lan Nguyễn | [ ] | 🟡 | Đã nộp, chờ review |
| **Bình Lê** | 2D | #42 | **122** | 6–8 | Lan Nguyễn | [ ] | 🔴 | Bị trả lại, xem [P-001](../problem-backlog.md#p-001) |
| **Bình Lê** | 2D | #42 | **123** | 9–11 | Lan Nguyễn | [ ] | 🔴 | Mới làm 1/3 ảnh |
| **Bình Lê** | 2D tracking | #44 | **126** | 0–59 | Lan Nguyễn | [ ] | 🔴 | Đang làm 1 track |
| **An Trần** | 2D tracking | #44 | **127** | 55–114 | Lan Nguyễn | [ ] | 🟡 | Đang làm |
| **An Trần** | 3D | #45 | **129** | 0–1 | Lan Nguyễn | [x] | 🟢 | Đã qua review |
| **Bình Lê** | 3D | #45 | **130** | 2–3 | Lan Nguyễn | [ ] | 🟡 | Đã nộp, chờ review |
| **An Trần** | 3D | #45 | **131** | 4–5 | Lan Nguyễn | [ ] | 🟡 | Đã nộp, chờ review |

🔴 0–50% · 🟡 >50–<100% · 🟢 100% · ⬜ chưa bắt đầu
