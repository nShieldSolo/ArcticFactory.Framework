# Báo cáo Chi phí Hàng tháng (Monthly Cost Report)

Báo cáo này liệt kê các khoản chi phí cố định tối thiểu để vận hành hệ thống hạ tầng và các công cụ AI hỗ trợ phát triển theo mô hình AI-First.

## 1. Chi phí Hạ tầng (Infrastructure)

- **Nhà cung cấp:** EZVPS
- **Gói dịch vụ (Tham khảo):** [Cấu hình VPS](https://my.ezvps.vn/cart.php?a=confproduct&i=2)
- **Mục đích sử dụng:** Deploy Backend (.NET Drop), Frontend (React), Database (PostgreSQL), và Redis Cache. Chạy Docker containers.
- **Chi phí dự kiến:** **550,000 VNĐ / tháng**

## 2. Chi phí Công cụ AI (AI Developer Tools)

- **Công cụ:** AI Code Antigravity (Mã nâng cấp: AGL1)
- **Gói dịch vụ:** Kèm link [Bảng giá tham khảo](https://docs.google.com/spreadsheets/d/1E5i9PVpCm925USx9jvxzJIXRKYRiDkb-_NPRjmfaKXY/edit?gid=113702909#gid=113702909)
- **Mục đích sử dụng:** Tự động hóa quá trình sinh code từ Requirement/Spec, Code Review, Refactoring và tối ưu hóa dự án AI-First.
- **Chi phí dự kiến:** **900,000 VNĐ / tháng**

## 3. Quản lý Mã nguồn & CI/CD

- **Công cụ:** GitLab
- **Gói dịch vụ:** Miễn phí (Free Tier)
- **Mục đích sử dụng:** Lưu trữ source code (Git repository) và cấu hình Auto DevOps / CI/CD pipeline.
- **Chi phí dự kiến:** **0 VNĐ / tháng**

---

### Tổng kết Chi phí Khởi điểm (Base Cost)

| Hạng mục | Chi phí (VNĐ/tháng) | Ghi chú |
| :--- | :--- | :--- |
| Hạ tầng VPS (EZVPS) | 550,000 | Server phục vụ Test/Staging/Production quy mô nhỏ |
| AI Tool (Mã AGL1) | 900,000 | License công cụ sinh code cho team |
| GitLab (CI/CD, Source) | 0 | Gói miễn phí |
| **Tổng cộng (Total)** | **1,450,000** | Khoản đầu tư cố định hàng tháng tối thiểu |

> *Lưu ý: Chi phí có thể thay đổi tùy thuộc vào biến động giá từ nhà cung cấp dịch vụ.*
