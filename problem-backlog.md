# Problem backlog

## Danh sách

| Mã | Tóm tắt | Loại | 2D/3D | Mục guideline | Trạng thái | Kết quả |
|---|---|---|---|---|---|---|
| [P-001](#p-001) | Người bị che 50–70% có gán `person` không? | Guideline mơ hồ | 2D | §3.2 | 🔴 Mở |  |

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
- **Kết quả:** 🔴 Mở
