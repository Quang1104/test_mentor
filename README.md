# Repo đội G03 (demo) — Cohort 4A

Repo làm việc của một đội gán nhãn, theo template repo đội của Cohort 4A.
Đây là **repo thử nghiệm cho MentorPrep**: tên người, số liệu và link CVAT đều là **giả**,
link CVAT trỏ tới một CVAT chạy local dùng để demo.

## Có gì trong repo

| Đường dẫn | Dùng để | Cập nhật khi nào |
|---|---|---|
| [`nhat-ky-tuan/`](nhat-ky-tuan/) | Ai giữ vị trí nào, được phân công gì, xong tới đâu | Đầu tuần phân công, cuối tuần chốt |
| [`problem-backlog.md`](problem-backlog.md) | Edge case gặp khi gán nhãn mà guideline chưa trả lời được, kèm link CVAT | **Ngay khi gặp** |
| [`so-quyet-dinh.md`](so-quyet-dinh.md) | Những gì đội đã chốt, và vì sao | Mỗi lần chốt một vấn đề |
| [`source-tool/`](source-tool/) | Source code công cụ đội tự viết để gỡ pain point khi gán nhãn | Khi đã xác định được pain point đáng làm tool |

## Các file nối với nhau thế nào

```mermaid
flowchart LR
    A[Gán nhãn trên CVAT] -->|gặp edge case| B[problem-backlog.md<br/>P-xxx + link CVAT]
    B -->|đội bàn và chốt| C[so-quyet-dinh.md<br/>QĐ-xxx]
    C -->|áp dụng lại| A
    B -->|pain point công cụ lặp lại| D[source-tool/]
    D -->|tool dùng khi gán| A
    B -.-> E[nhat-ky-tuan/<br/>tổng kết tuần]
    C -.-> E
```

## Thành viên

| Thành viên | Vị trí |
|---|---|
| Lan Nguyễn | Lead, Reviewer |
| An Trần | Annotator |
| Bình Lê | Annotator |

| Vị trí | Việc chính |
|---|---|
| **Lead** | Chia job, điều phối, đưa edge case ra bàn và chốt, giữ sổ quyết định |
| **Annotator** | Gán nhãn theo guideline; gặp chỗ guideline không trả lời được thì ghi vào backlog thay vì tự đoán |
| **Reviewer** | Kiểm job đã gán, trả lại chỗ sai kèm lý do |

Một người có thể giữ nhiều vị trí, nhưng **không review job do chính mình gán**.

## Quy ước

- **Mã**: `P-001`, `QĐ-001`, đánh số tăng dần. Không dùng lại số của mục đã bỏ.
- **Link CVAT**: trỏ tới đúng job và frame (`.../jobs/<id>?frame=<n>`), không trỏ tới cả task.
- **Mục guideline**: ghi số mục (`§3.2`) để ai cũng tra lại được.
- **Loại công việc**: ghi rõ **2D** hay **3D** (tracking là 2D video hoặc 3D theo frame).
