# Test Data Catalog — v2.0

> Tạo bởi: analyze-requirements. Dữ liệu test (valid / invalid / boundary) per module, trích từ DOC-v2.0-01.
> `req_notation: none` → cột Nguồn dùng `§section` reference (không có số FR/VR/AC/UC trong doc).
>
> **Structure-lock:** giữ nguyên 5 cột `| Field | Valid | Invalid | Boundary | Nguồn |` cho mọi module.

## Module DASH — Dashboard (DOC-v2.0-01)

| Field | Valid | Invalid | Boundary | Nguồn |
|-------|-------|---------|----------|-------|
| User session | Đã đăng nhập, token còn hạn | Chưa đăng nhập (→ redirect login) | — | §Đặc tả chức năng · §DASHBOARD · Table 5 "Pre-Conditions" |
| Quyền Dashboard | User có quyền truy cập Dashboard | User không có quyền (→ từ chối/ẩn menu) | — | §Đặc tả chức năng · §DASHBOARD · Table 5 "Actor" |
| Trạng thái dữ liệu backend | Dữ liệu đã sync đầy đủ | Backend chưa sync (→ loading state / empty state) | — | §Đặc tả chức năng · §DASHBOARD · Table 5 "Pre-Conditions" |

## Module CH — Cơ hội: Tạo cơ hội (DOC-v2.0-01)

| Field | Valid | Invalid | Boundary | Nguồn |
|-------|-------|---------|----------|-------|
| MST khách hàng | MST hợp lệ đã có trong CSDL (→ auto-fill thông tin) | MST không tồn tại (→ không tìm thấy, chuyển flow KH mới) | — | §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 "Bước 2" |
| Tên khách hàng | Tên KH hợp lệ, tồn tại trong CSDL | Tên rỗng (→ báo lỗi); tên không khớp (→ 0 kết quả) | — | §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 "Bước 1" |
| Quyền "Tạo cơ hội" | User có quyền "Tạo cơ hội" | User không có quyền (→ từ chối, ẩn button) | — | §Đặc tả chức năng · §TẠO CƠ HỘI · Table 6 "Pre-Conditions" |
| KH có CĐ đang mở | KH không có CĐ nào đang mở (→ tạo thẳng) | — | — | §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 "Bước 6" |
| Loại dịch vụ (khi CĐ trùng) | Loại DV khác với CĐ đang mở (→ tạo thẳng) | Loại DV trùng + khác AM (→ phân luồng duyệt) | — | §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 "Bước 7" |
| AM của cơ hội | Cùng AM với CĐ trùng (→ tạo thẳng) | Khác AM + cùng TTKD (→ duyệt cùng TT); khác AM + khác TTKD (→ duyệt khác TT) | — | §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 "Bước 8-9" |
| Doanh thu kỳ vọng | Giá trị số dương, ≤ 300.000.000 (→ duyệt cấp thấp) | Giá trị âm hoặc 0 (→ validation error) | **300.000.000 (ranh giới phân luồng duyệt)** | §Danh sách chức năng · Table 4 "Phê duyệt yêu cầu" |

## Module PDC — Phê duyệt cơ hội (DOC-v2.0-01)

| Field | Valid | Invalid | Boundary | Nguồn |
|-------|-------|---------|----------|-------|
| Doanh thu kỳ vọng (phân luồng) | ≤ 300M (→ phân luồng cấp thấp); > 300M (→ phân luồng cấp cao) | — | **300.000.000 đồng (phân luồng duyệt)** | §Danh sách chức năng · Table 4 "Phê duyệt yêu cầu" |
| Giá trị báo giá (hạn mức) | ≤ hạn mức cài đặt (→ AM tự chốt) | > hạn mức (→ routing BGĐ TTKD phê duyệt) | **Giá trị hạn mức được QA cấu hình trong Cài đặt** | §Danh sách chức năng · Table 4 "Phê duyệt báo giá" |
| Loại dịch vụ + Vùng miền (TPKT) | Loại DV + Vùng miền có TPKT tương ứng (→ phân công đúng) | Loại DV + Vùng miền không match TPKT nào (→ cần clarification) | — | §Danh sách chức năng · Table 4 "Phê duyệt giải pháp" |
| Quyết định phê duyệt | Approve (→ kích hoạt bước tiếp) | Reject (→ trả về AM để sửa) | — | §Danh sách chức năng · Table 4 "Phê duyệt giải pháp" |

## Module BC — Báo cáo (DOC-v2.0-01)

| Field | Valid | Invalid | Boundary | Nguồn |
|-------|-------|---------|----------|-------|
| Document ID (tra cứu báo giá) | ID hợp lệ, tồn tại trong log (→ hiển thị thông tin) | ID không tồn tại (→ "không tìm thấy"); ID rỗng (→ validation) | — | §Danh sách chức năng · Table 4 "Tra cứu báo giá" |
| Ngày hết hạn HĐ/PL | HĐ hết hạn trong 60 ngày (→ xuất hiện trong BC) | HĐ hết hạn > 60 ngày (→ không xuất hiện) | **60 ngày (in report), 61 ngày (out); 30 ngày; 15 ngày** | §Danh sách chức năng · Table 4 "Báo cáo doanh thu gia hạn" |

## Module CD — Cài đặt & Cấu hình (DOC-v2.0-01)

| Field | Valid | Invalid | Boundary | Nguồn |
|-------|-------|---------|----------|-------|
| Hạn mức phê duyệt báo giá | Giá trị tiền hợp lệ > 0, theo từng loại DV | Giá trị âm hoặc 0 (→ validation); giá trị quá cao không hợp lý | **Giá trị biên tùy thuộc rule nghiệp vụ (pending spec)** | §Danh sách chức năng · Table 4 "Thiết lập hạn mức báo giá" |
| Tiêu chí đánh giá | Tiêu chí có tên, mô tả rõ ràng | Tên tiêu chí rỗng (→ validation) | — | §Danh sách chức năng · Table 4 "Thiết lập tiêu chí đánh giá" |
| Trạng thái notification | Chưa đọc (badge tăng); Đã đọc (badge giảm) | — | — | §Danh sách chức năng · Table 4 "Notification" |

## Module KH — Khách hàng / Lead / CV / DH (DOC-v2.0-01)

| Field | Valid | Invalid | Boundary | Nguồn |
|-------|-------|---------|----------|-------|
| Loại khách hàng | Cá nhân; Doanh nghiệp trong nước; Tổ chức nước ngoài; Cơ quan nhà nước; Hộ kinh doanh | Loại không thuộc danh sách (→ validation) | — | §Đặc tả chức năng · §TẠO CƠ HỘI · wireframe refs (para 62-76) |
| MST khách hàng | MST hợp lệ (10 số đối với DN trong nước) | MST sai format; MST đã tồn tại trong hệ thống (→ duplicate warning) | — | §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 "Bước 1" |
| Trạng thái Lead | Lead mới từ CRM; Lead đang khai thác; Lead thành công; Lead thất bại | — | — | §Danh sách chức năng · Table 4 "Lead" |

## Ghi chú chung

- Giá trị "master data" (danh mục loại DV, vùng miền, TTKD) phụ thuộc môi trường STG — xác nhận giá trị thực khi vibe-test/automation.
- Boundary values (in **đậm**) là ứng viên chính cho BVA ở generate-tc. Mốc quan trọng nhất: **300.000.000 đồng** (phân luồng phê duyệt).
- Field validation chi tiết (độ dài, format) chưa có spec cho hầu hết modules → cần BA bổ sung trước generate-tc (liên quan C-CH-001).

### Quy ước cell

- **Valid:** giá trị hợp lệ (mô tả) + kết quả dự kiến
- **Invalid:** giá trị không hợp lệ (→ hệ quả)
- **Boundary:** **bold** giá trị biên + (hợp lệ/chặn)
- **Nguồn:** `§section` (req_notation: none)
