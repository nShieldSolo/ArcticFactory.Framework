# 📌 ArcticFactory — NK Tech AI-First Framework
Chào mừng bạn đến với trung tâm tài liệu quy chuẩn kỹ thuật của hệ thống Bắc Cực (ArcticFactory). Trang Index này giúp bạn định vị nhanh các tài liệu, sơ đồ, báo cáo và biểu mẫu cần thiết trong quá trình phát triển mã nguồn cùng AI.

---

## 📖 1. Tài Liệu Cốt Lõi (Core Framework)
Những tài liệu xương sống định hình toàn bộ chuẩn mực code, workflow và cách AI sinh code.
- 🔗 **[`framework-specification.md`](./framework-specification.md)**: **Bản Đặc Tả Yêu Cầu Framework (v2.1)** — Chi tiết toàn bộ kiến trúc, SLA, CI/CD, Guardrails, AI Prompt mẫu và Luồng quản lý dự án (Artifact 0-8). Đọc file này trước khi code.
- 🔗 **[`developer_collaboration_workflow.md`](./developer_collaboration_workflow.md)**: Sơ đồ tương tác chi tiết giữa Backend Dev, Frontend Dev và quá trình tự động sinh TS Client (Swagger). Chi tiết các zone hoạt động riêng rời cho từng mảng.

---

## 💸 2. Thông tin Vận hành & Đầu tư
Các quy hoạch nguồn vốn tối thiểu cần thiết để vận hành dự án.
- 🔗 **[`cost-summary.md`](./cost-summary.md)**: Báo cáo chi tiêu Hạ tầng (VPS) và License Code AI (AGL1 Tools) hàng tháng của dự án, cùng tuỳ chọn CI/CD GitLab nội bộ.

---

## 🗂️ 3. Thư Viện Biểu Mẫu (Templates)
Các file Markdown dùng chung để thống nhất định dạng input/output giữa Business Analyst và Developer trước khi giao cho AI thực thi.
> **Vị trí**: Nằm trong thư mục `/template`

- 📝 **[`00_BRD_Template.md`](./template/00_BRD_Template.md)**: Bản gốc từ BA, bao gồm User Stories, Wireframes, và tiêu chí nghiệm thu (Acceptance Criteria).
- 📝 **[`01_PRD_Template.md`](./template/01_PRD_Template.md)**: Ticket kỹ thuật được cắt ra từ BRD để chia Scope cho Dev theo từng giai đoạn (Phase).
- 📝 **[`02_BE_Spec_Template.md`](./template/02_BE_Spec_Template.md)**: Đặc tả của Endpoint Backend. Dùng để cấu hình Input / Output, Rule logic cho AI tự generate C# API.
- 📝 **[`06_FE_Spec_Template.md`](./template/06_FE_Spec_Template.md)**: Đặc tả định tuyến linh kiện Frontend. AI dùng để mapping trường API Auto-generated và React UI Components.
- 📝 **[`08_AI_Rules_Template.md`](./template/08_AI_Rules_Template.md)**: File cấu hình Global. Set up chuẩn Result<T>, FluentValidation,... cho Agent trước khi thực tế build code.

---

## 🎨 4. Sơ đồ Luồng Trực Quan (Visual Flow)
Dành cho người mới tiếp cận để hiểu chu trình chạy của các thành viên.
- 🖼️ **[`nk_tech_framework_summary_vn.png`](./images/nk_tech_framework_summary_vn.png)**: Sơ đồ dạng phác thảo đơn giản (Cheat Sheet) ghi nhớ Input/Output của 4 bước: BA ➔ Dev ➔ Agent ➔ Automation.
- 🖼️ **[`nk_tech_simple_with_ba.png`](./images/nk_tech_simple_with_ba.png)**: Khái quát ngắn ngọn vị trí của Business Analyst đóng vai trò tạo mầm (Seed) thay vì chỉ giao thẳng cho lập trình.
- 🌐 **[`nk_tech_io_flow_detailed.html`](./nk_tech_io_flow_detailed.html)**: Trang Infographic chi tiết theo dạng khối HTML rõ ràng hơn khi cần phân tích Output của từng vai trò.

---
> *Đây là thư viện tài liệu SỐNG. Mọi người chịu trách nhiệm update Template/Hướng dẫn tương tự như việc duy trì mã nguồn (Documentation as Code).*
