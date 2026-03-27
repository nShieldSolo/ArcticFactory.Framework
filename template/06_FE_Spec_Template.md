# FE Spec: {Tên Trang / Tính Năng}

## 1. Thông tin chung
- Giao diện: Trang danh sách / Form Edit / Modal...
- Reference: BRD-{Mã}, Mockup/Figma Link: [Figma](...)
- API sử dụng: `apiClient.{hàm}()` (Auto-generated từ Swagger)
- Người sở hữu: {Tên Frontend Dev}

## 2. Component Layout (Hình thức bố cục)
{Phác thảo cấu trúc thành phần UI hiển thị}
- **Header**: Tiêu đề trang + Breadcrumb + Action Button (Kế thừa từ US-X).
- **Phần thân**:
  - Filter Bar: Gồm các dropdown bộ lọc / input tìm kiếm.
  - Data Table: Gồm n cột (Mapping trong phần dưới).
- **Footer**: Thanh phân trang (Pagination).

## 3. Data Mapping (Cấu trúc dữ liệu)
{Chuyển đổi dữ liệu từ API sang Layout}
- Hàm gọi API: `featureApi.getFeatureList({ params... })`
- Mapping dữ liệu bảng:
  | Tên hiển thị (Cột) | Map Field (JSON) | Định dạng (Formatter) |
  |--------------------|------------------|-----------------------|
  | Mã Số              | `id`             | Cắt ngắn 8 ký tự đầu  |
  | Giá (VND)          | `price`          | Thêm đ/cách ngàn      |
  | Trạng thái         | `status`         | Hiển thị thẻ Badge    |

## 4. UX States (Luồng Trạng Thái UI)

| State         | Mô tả UI hiển thị                           | Hành động                   |
|---------------|---------------------------------------------|-----------------------------|
| **Loading**   | Hiển thị Skeleton thay vì Spinner.          | Vô hiệu hóa Search Button.  |
| **Empty**     | "Không tìm thấy kết quả" + Icon.            | Hiển thị lúc Table trống.   |
| **Error**     | Toast màu đỏ "Lỗi hệ thống 500".            | Nút "Thử lại (Retry)".      |
| **Success**   | Bảng hiện đầy đủ dữ liệu / Form báo Xong.   | Redirect (nếu là form).     |

## 5. Interaction (Tương tác động)
- Khi đổi filter: Lập tức gọi lại API.
- Phân trang: Đổi parameter trên URL, refetch dữ liệu.
- Click Table Row: Navigate đến `/route/{id}` chi tiết.

## 6. Kiến trúc Thư Mục (Gợi ý cấu trúc khi Gen AI)
```
FeatureFolder/
├── DefaultPage.tsx          ← Component Root
├── ViewComponent.tsx        ← Hiển thị UI logic
├── ActionFilter.tsx         ← Tìm kiếm filter
└── useFeatureLogic.ts       ← Hook quản lý API state
```
