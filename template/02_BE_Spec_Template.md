# BE Spec: {Tên Tính Năng}

## 1. Thông tin chung
- Mô tả: Lấy danh sách, cập nhật, tạo mới... {Mục đích của Backend}
- Reference: BRD-{Mã}, PRD-{Mã}
- Người sở hữu: {Tên Backend Dev}

## 2. HTTP Endpoint
- **Method**: `GET / POST / PUT / DELETE`
- **Route**: `/api/v1/{resource}`
- **Auth**: Required / AllowAnonymous — **Policy**: `"CanManageX"`

## 3. Input (Request DTO / Parameters)

| Param/Field | Type   | Required | Trạng thái (Default/Enum) | Ràng buộc (Constraint)|
|-------------|--------|----------|---------------------------|-----------------------|
| field1      | string | Yes      |                           | MaxLength(100)        |
| page        | int    | No       | 1                         | >= 1                  |

## 4. Output (200 OK / Response DTO)

```json
{
  "items": [
    {
      "id": "uuid",
      "name": "string",
      "createdAt": "2026-03-27T10:00:00Z"
    }
  ],
  "totalCount": 0,
  "currentPage": 1,
  "totalPages": 1
}
```

## 5. Quy tắc Kinh doanh Biên (Business Rules / Edge cases)
{Liệt kê các rule AI cần sinh code bằng FluentValidation hoặc Handler Logic.}
1. Nếu `fieldX` = "A" thì `fieldY` bắt buộc phải có giá trị.
2. Sắp xếp mặc định theo `createdAt` giảm dần (DESC).
3. Pagination tối đa `pageSize` = 100.

## 6. Error Cases (Exception / Result Pattern)
{Thiết lập mã lỗi nếu validation thất bại hoặc không tìm thấy dữ liệu.}

| Tình huống             | HTTP Code | Error Code         | Error Message             |
|------------------------|-----------|--------------------|---------------------------|
| Validation Data lỗi    | 400       | VALIDATION.INVALID | Thông tin không hợp lệ    |
| Bản ghi bị xoá         | 404       | RESOURCE.NOT_FOUND | Không tìm thấy {resource} |
| Không đủ quyền Admin   | 403       | AUTH.FORBIDDEN     | Không có quyền truy cập   |
