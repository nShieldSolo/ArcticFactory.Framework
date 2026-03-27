# PRD-{Mã}: {Tên Tính Năng} (Giai đoạn {Number})

**Nguồn tham chiếu (Ref):** BRD-{Mã} Khác
**Sprint:** {Sprint Number} | **Priority:** {P0/P1...}

## 1. Scope (Phạm vi)
{Mô tả ngắn gọn phạm vi phát triển trong ticket này. Đây là US nào, thuộc Phase nào của BRD?}
- US-... (BRD-...): Giao diện / Tính năng [Action]

## 2. Acceptance Criteria (Kế thừa từ BRD)
{Liệt kê lại các AC cụ thể cần thực hiện trong scope này.}
- **AC-X**: {Chi tiết}
- **AC-Y**: {Chi tiết}

## 3. Task Breakdown (Dev tasks)
{Tách thành các nhiệm vụ kỹ thuật cụ thể cho BE và FE.}

### Backend Tasks
- [ ] API: Tạo endpoint `[HTTP_METHOD] /api/v1/[...` đáp ứng AC-...
- [ ] Logic/DB: Cập nhật migration, kiểm tra rule logic kinh doanh.

### Frontend Tasks
- [ ] UI: Tạo component hiển thị theo wireframe/Figma.
- [ ] API Client: Tích hợp API auto-gen, xử lý state Loading/Error.

## 4. Definition of Done (Tiêu chuẩn Hoàn thành)
{Checklist nghiệm thu cho Developer/Tester.}
- [ ] BE API hoạt động đúng các AC.
- [ ] BE / FE Spec được tạo/cập nhật đầy đủ.
- [ ] FE UI match wireframe trong BRD.
- [ ] Unit test (BE) + Component test (FE) đạt pass 100%.
- [ ] Pipeline CI Xanh.
- [ ] Tech Lead đã review code (AI generated code cũng phải được human duyệt).
