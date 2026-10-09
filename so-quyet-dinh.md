# Sổ quyết định

## Danh sách

| Mã | Quyết định | Ngày | Xuất phát từ | Trạng thái |
|---|---|---|---|---|
| [QĐ-001](#qđ-001) | Người bị che dưới 70% vẫn gán `person` + `occluded` | 09/10/2026 | [P-001](problem-backlog.md#p-001) | Hiệu lực |
| [QĐ-002](#qđ-002) | Cuboid `pedestrian` khi điểm thưa: cao 1.6–1.8 m | 09/10/2026 | [P-002](problem-backlog.md#p-002) | Hiệu lực |

**Trạng thái:** Hiệu lực · Bị thay bởi QĐ-xxx · Huỷ (ghi lý do)

---

## QĐ-001

**Người bị che dưới 70% vẫn gán `person` và bật `occluded`**

- **Ngày:** 09/10/2026
- **Người tham gia:** Mentor (chốt), Lan Nguyễn, Bình Lê
- **Xuất phát từ:** [P-001](problem-backlog.md#p-001)
- **Bối cảnh:** Guideline §3.2 không ghi ngưỡng che khuất.
- **Các phương án đã cân nhắc:**
  1. *Bỏ qua khi che từ 50%* — mất nhiều người đi bộ ở góc đường. Loại.
  2. *Bỏ qua khi che trên 70%, còn lại gán + `occluded`* — **Chọn.**
- **Quyết định:** Đối tượng bị che dưới 70% vẫn gán bình thường và bật thuộc tính `occluded`.
- **Việc phải làm theo:**
  - Bình sửa lại job 122 rồi nộp duyệt lại.
- **Trạng thái:** Hiệu lực

## QĐ-002

**Point cloud thưa: cuboid `pedestrian` cao 1.6–1.8 m, bám tâm theo điểm**

- **Ngày:** 09/10/2026
- **Người tham gia:** Mentor (chốt), Lan Nguyễn, An Trần
- **Xuất phát từ:** [P-002](problem-backlog.md#p-002)
- **Bối cảnh:** Guideline §5.1 chỉ nói "cuboid ôm sát điểm", không nói trường hợp điểm quá thưa.
- **Các phương án đã cân nhắc:**
  1. *Bám đúng điểm* — ra kích thước vô lý (2.4 m). Loại.
  2. *Chiều cao chuẩn 1.6–1.8 m, tâm theo điểm* — **Chọn.**
- **Quyết định:** Khi người đi bộ có quá ít điểm, đặt chiều cao 1.6–1.8 m, rộng/dài khoảng 0.6 m, tâm đặt theo cụm điểm.
- **Việc phải làm theo:**
  - An sửa lại job 131.
- **Trạng thái:** Hiệu lực
