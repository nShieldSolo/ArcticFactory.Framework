# NK Tech AI-First Rules (.ai-rules.md)

> File này cung cấp context ngữ cảnh (Guardrails) để mọi AI Assistant (Copilot, Cursor, r-Agent, ChatGPT) tuân thủ khi viết mã nguồn cho Framework này.

## Ngôn Ngữ & Môi Trường
- **C# / .NET 10** (Minimal API) + Entity Framework Core + PostgreSQL.
- **React / TypeScript** (Next.js / Vite tuỳ chọn dự án) + Auto-gen API Client.

## 1. Backend Rules (C# .NET)
- SỬ DỤNG **`Result<T>` pattern** thay vì throw Exception với lỗi nghiệp vụ/Validation. Ngoại trừ hệ thống vỡ (DB chết), tuyệt đối không throw Exception bên trong Business Logic.
- TỰ ĐỘNG BẢO MẬT: Mọi request phải validate input qua `FluentValidation`.
- I/O BẤT ĐỒNG BỘ: Database I/O, Network Calls (HTTP request, Caching Redis) **luôn luôn** dùng ASYNC/AWAIT.
- TRUY VẤN TỐI ƯU: Chặn triệt để lỗi N+1 qua `.Include()` / Explicit Join / `.Select(Projection)`.
- CẤU TRÚC FOLDER FEATURE: Max 200 dòng 1 file. {Endpoint, Handler, Response, Validator} gom chung một feature folder. Không references chéo.

## 2. Frontend Rules (React/TS)
- STRICT MODE BẬT: KHÔNG dùng kiểu `any`. Định nghĩa Interface/Type TS rõ ràng nếu code auto gen không bao hàm.
- NO MANUAL FETCH: **Luôn luôn** phụ thuộc vào auto-gen Api Client Swagger thay vì viết Axios thủ công. Chờ swagger.json đẩy sang để dùng.
- SINGLE RESPONSIBILITY COMPONENT: Chia nhỏ component. Trạng thái (Hooks, API call) được đẩy ra file logic `useFeatureLogic.ts` độc lập.
- CSS/STYLING: Tuân thủ design utility framework dự án sử dụng. Tránh hard-coding style inline.

## 3. Quy trình Trách Nhiệm (Accountability Workflow)
- Khi Human yêu cầu tạo code, **AI bắt buộc phải đọc BE Spec / FE Spec .md trước tiên**. Mọi đoạn code sinh ra phải thoả mãn Specification đó.
- Không sửa file API client đã Auto Generated. 
- Mọi logic có dính Secret, Environment keys tuyệt đối dùng biến môi trường, không lưu hardcode chuỗi string bí mật trong code.

---
> Nhắc nhẹ AI: "Sứ mệnh của bạn là một người thực thi đáng tin cậy. Dịch yêu cầu từ file Markdown (Spec) ra File Code theo đúng kiến trúc thiết kế System trên, chính xác, sạch đẹp và đúng chuẩn mực."
