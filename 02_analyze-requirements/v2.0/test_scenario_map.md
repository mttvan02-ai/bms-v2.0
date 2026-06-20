# Test Scenario Map — v2.0

## Tổng quan
- Tổng số scenarios: 40 (NEW: 40, MODIFIED: 0, CARRIED: 0)
- Phân bổ priority: P1: 12 | P2: 23 | P3: 5

---

## Scenarios — NEW (chi tiết đầy đủ)

### DASH — Dashboard

| Scenario ID | Feature | Req ID | DOC Source | Given | When | Then | Priority | Test Type | Lifecycle |
|-------------|---------|--------|-----------|-------|------|------|----------|-----------|-----------|
| SC-DASH-001 | Dashboard auto-display | REQ-DASH-001 | DOC-v2.0-01 | User đã đăng nhập thành công | Hệ thống hoàn tất quá trình login | Màn hình Dashboard tự động hiển thị với đầy đủ widget theo quyền user | P1 | Functional | NEW |
| SC-DASH-002 | KPI stats theo phân quyền | REQ-DASH-002 | DOC-v2.0-01 | User đã đăng nhập và có quyền Dashboard | Dashboard đang hiển thị | Hiển thị đủ 5 KPI stats (KHTN mới, CĐ mới, CĐ chờ duyệt, DT dự kiến, Tỷ lệ thành công) và dữ liệu khớp với phân quyền user | P1 | Functional | NEW |
| SC-DASH-003 | Click menu Dashboard | REQ-DASH-001 | DOC-v2.0-01 | User đã đăng nhập, đang ở màn hình khác | User click menu "Dashboard" | Hệ thống navigate đến màn hình Dashboard, hiển thị đầy đủ widget | P2 | Functional | NEW |
| SC-DASH-004 | Biểu đồ & chart | REQ-DASH-002 | DOC-v2.0-01 | Dashboard đang hiển thị với dữ liệu từ backend | User xem Dashboard | Hiển thị đúng: Nhóm DV phổ biến, Cơ hội theo thời gian, Trạng thái CĐ, Doanh thu theo nhóm DV | P2 | Functional | NEW |
| SC-DASH-005 | Top 5 CĐ + Lý do đóng | REQ-DASH-002 | DOC-v2.0-01 | Dashboard hiển thị với dữ liệu từ backend | User xem Dashboard | Top 5 cơ hội doanh thu cao nhất hiển thị đúng thứ tự; Lý do đóng cơ hội hiển thị | P2 | Functional | NEW |
| SC-DASH-006 | Tương tác widget | REQ-DASH-003 | DOC-v2.0-01 | Dashboard hiển thị với đầy đủ widget | User click vào widget/biểu đồ để lọc/xem chi tiết | Hệ thống phản hồi tương tác: lọc dữ liệu hoặc điều hướng đến màn hình chi tiết tương ứng | P3 | Functional | NEW |

#### Source Detail per Scenario — DASH

##### SC-DASH-001 — Dashboard auto-display sau login

**Source Quote:**
> "Trigger: Người dùng đăng nhập hệ thống thành công hoặc click vào menu "Dashboard"."
> "Post-Conditions: Hiển thị các widget/biểu đồ/tổng hợp dữ liệu theo quyền user"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §DASHBOARD · Table 5 · rows "Trigger" + "Post-Conditions"`

**Analyst Note:** Trigger #1 trong 2 trigger. Login thành công → hệ thống mặc định hiển thị Dashboard. Cần test rằng Dashboard là landing page sau login, không phải page khác.

---

##### SC-DASH-002 — KPI stats hiển thị đầy đủ theo phân quyền

**Source Quote:**
> "Thống kê: Khách hàng tiềm năng mới. Cơ hội mới, Cơ hội chờ duyệt, Doanh thu dự kiến, Tỷ lệ cơ hội thành công"
> "Actor: Theo ma trận phân quyền sẽ xem được các dữ liệu tương ứng."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §DASHBOARD · Table 5 · rows "Description" + "Actor"`

**Analyst Note:** 5 KPI cụ thể. Dữ liệu filter theo quyền → mỗi role thấy data scope khác nhau. Pending C-DASH-001 (ma trận phân quyền) để verify expected data per role.

---

##### SC-DASH-006 — Tương tác widget

**Source Quote:**
> "Post-Conditions: Người dùng có thể tương tác (lọc, xem chi tiết)"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §DASHBOARD · Table 5 · row "Post-Conditions"`

**Analyst Note:** URD nêu "lọc, xem chi tiết" nhưng không specify widget nào có tương tác nào. Test at high level: ít nhất 1 widget có thể interact được. Chi tiết pending spec.

---

### CH — Cơ hội

#### CH — Tạo cơ hội

| Scenario ID | Feature | Req ID | DOC Source | Given | When | Then | Priority | Test Type | Lifecycle |
|-------------|---------|--------|-----------|-------|------|------|----------|-----------|-----------|
| SC-CH-001 | Tạo CĐ - KH cũ, không trùng | REQ-CH-004 | DOC-v2.0-01 | User có quyền "Tạo cơ hội", KH đã có trong CSDL, KH chưa có CĐ đang mở | User nhập thông tin CĐ, tìm KH bằng MST/tên → KH found → submit | Hệ thống tạo CĐ thành công với status "Mới"; notification gửi Sale Manager; CĐ xuất hiện trong danh sách | P1 | Functional | NEW |
| SC-CH-002 | Tạo CĐ - KH cũ, CĐ đang mở, khác DV | REQ-CH-004 | DOC-v2.0-01 | User có quyền, KH có CĐ đang mở với loại DV khác | User tạo CĐ mới cho KH, loại DV khác DV của CĐ đang mở | Hệ thống check step 7 → DV không trùng → tạo CĐ thành công | P1 | Functional | NEW |
| SC-CH-003 | Tạo CĐ - cùng DV, cùng AM | REQ-CH-004 | DOC-v2.0-01 | User là AM của CĐ đang mở, KH có CĐ đang mở cùng loại DV | User (cùng AM) tạo CĐ mới cùng loại DV cho KH | Hệ thống step 8 → cùng AM → tạo CĐ thành công | P1 | Functional | NEW |
| SC-CH-004 | Tạo CĐ - khác AM, cùng TTKD | REQ-CH-004 | DOC-v2.0-01 | AM mới và AM của CĐ trùng thuộc cùng TTKD, KH có CĐ đang mở cùng loại DV | AM mới tạo CĐ cho KH với DV trùng | Hệ thống step 9 → cùng TTKD → phân luồng quy trình duyệt CĐ trùng cùng TTKD | P1 | Functional | NEW |
| SC-CH-005 | Tạo CĐ - khác AM, khác TTKD | REQ-CH-004 | DOC-v2.0-01 | AM mới và AM của CĐ trùng thuộc TTKD khác nhau, KH có CĐ đang mở cùng loại DV | AM mới tạo CĐ cho KH với DV trùng | Hệ thống step 9 → khác TTKD → phân luồng quy trình duyệt CĐ trùng khác TTKD | P1 | Functional | NEW |
| SC-CH-006 | Tạo CĐ - KH mới | REQ-CH-004 | DOC-v2.0-01 | User có quyền, KH chưa tồn tại trong CSDL | User nhập MST/tên → không tìm thấy → nhập thông tin KH mới → submit | Hệ thống tạo KHTN mới đồng thời với tạo CĐ (step 5); CĐ và KHTN cùng lúc xuất hiện trong hệ thống | P1 | Functional | NEW |
| SC-CH-007 | Tìm KH bằng MST | REQ-CH-004 | DOC-v2.0-01 | User đang trong form Tạo CĐ, KH tồn tại trong CSDL | User nhập MST của KH vào ô tìm kiếm | Hệ thống tìm thấy KH, tự động điền thông tin KH vào form (step 3) | P2 | Functional | NEW |
| SC-CH-008 | Tìm KH bằng tên | REQ-CH-004 | DOC-v2.0-01 | User đang trong form Tạo CĐ, KH tồn tại trong CSDL | User nhập tên KH vào ô tìm kiếm | Hệ thống tìm thấy KH, tự động điền thông tin (step 3); nếu nhiều kết quả → cho phép chọn | P2 | Functional | NEW |
| SC-CH-009 | Validation trường bắt buộc | REQ-CH-001 | DOC-v2.0-01 | User đang trong form Tạo CĐ | User bỏ trống trường bắt buộc và submit | Hệ thống hiển thị thông báo lỗi validation, không tạo CĐ, highlight field lỗi | P2 | Functional | NEW |
| SC-CH-010 | User không có quyền Tạo CĐ | REQ-CH-002 | DOC-v2.0-01 | User đã đăng nhập nhưng không có quyền "Tạo cơ hội" | User truy cập chức năng Tạo CĐ | Hệ thống từ chối truy cập (button ẩn hoặc redirect về unauthorized) | P2 | Functional | NEW |
| SC-CH-011 | Notification gửi Sale Manager | REQ-CH-003 | DOC-v2.0-01 | CĐ vừa được tạo thành công | Hệ thống xử lý sau tạo CĐ | Notification được gửi đến Sale Manager (xem tại icon chuông hoặc email) | P2 | Functional | NEW |
| SC-CH-012 | CĐ xuất hiện trong danh sách | REQ-CH-003 | DOC-v2.0-01 | CĐ vừa được tạo thành công với status "Mới" | User vào Danh sách cơ hội | CĐ mới xuất hiện trong danh sách với status "Mới" | P2 | Functional | NEW |

#### CH — Danh sách cơ hội

| Scenario ID | Feature | Req ID | DOC Source | Given | When | Then | Priority | Test Type | Lifecycle |
|-------------|---------|--------|-----------|-------|------|------|----------|-----------|-----------|
| SC-CH-013 | Danh sách CĐ theo tiến trình | REQ-CH-005 | DOC-v2.0-01 | User có quyền xem Danh sách cơ hội | User vào màn hình Danh sách cơ hội | Hiển thị CĐ phân loại theo tiến trình (Khai thác → review HĐ → Tạo HĐ → Triển khai → Xuất HĐ → Kết thúc) | P2 | Functional | NEW |
| SC-CH-014 | Lọc nâng cao danh sách CĐ | REQ-CH-005 | DOC-v2.0-01 | Đang ở màn hình Danh sách cơ hội | User sử dụng bộ lọc nâng cao (theo module/field) | Danh sách lọc đúng theo tiêu chí; kết quả cập nhật | P2 | Functional | NEW |
| SC-CH-015 | Xuất Excel danh sách CĐ | REQ-CH-005 | DOC-v2.0-01 | Đang ở màn hình Danh sách cơ hội | User click nút Xuất Excel | File Excel được tải về với đầy đủ dữ liệu danh sách CĐ | P3 | Functional | NEW |

#### Source Detail per Scenario — CH Tạo CĐ

##### SC-CH-001 — Tạo CĐ happy path - KH cũ, không trùng

**Source Quote:**
> "Bước 1: Người dùng chọn tạo cơ hội, nhập thông tin cơ hội, nhập MST hoặc tên khách hàng để tìm kiếm thông tin khách hàng.
> Bước 2: Hệ thống tìm kiếm khách hàng bằng MST/tên khách hàng: Nếu KH đã có trong CSDL: chuyển đến bước 3
> Bước 3: Hệ thống tự động điền thông tin KH bằng thông tin đã lưu trong CSDL
> Bước 6: Hệ thống check nếu KH đang có cơ hội ĐANG MỞ: Nếu không: hệ thống tạo cơ hội và hoàn tất quy trình."
> "Post-Conditions: Cơ hội mới được tạo với trạng thái "Mới" hoặc stage được chọn • Hệ thống gửi notification đến Sale Manager • Cơ hội xuất hiện trong Danh sách cơ hội"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 rows 1,2,3,6 + Table 6 row "Post-Conditions"`

**Analyst Note:** Happy path chính. Luồng: step 1 → 2 (KH found) → 3 (auto-fill) → 4 (submit) → 6 (không có CĐ đang mở) → tạo thành công. Test verify: form auto-fill đúng, status = "Mới", notification gửi, xuất hiện danh sách.

---

##### SC-CH-004 — Tạo CĐ - khác AM, cùng TTKD → phân luồng duyệt

**Source Quote:**
> "Bước 9: Hệ thống kiểm tra TTKD của AM:
> Nếu AM của cơ hội mới và AM của cơ hội trùng cùng TTKD: hệ thống đi theo quy trình duyệt cơ hội trùng cùng TTKD."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 · row "Bước 9"`

**Analyst Note:** Trigger quy trình duyệt đặc biệt khi CĐ trùng loại DV + khác AM + cùng TTKD. Quy trình duyệt chi tiết chưa có spec → C-CH-003. Test chỉ verify rằng hệ thống ROUTING đến đúng quy trình duyệt, không verify nội dung quy trình đó.

---

##### SC-CH-005 — Tạo CĐ - khác AM, khác TTKD → phân luồng duyệt

**Source Quote:**
> "Bước 9: Hệ thống kiểm tra TTKD của AM:
> Nếu AM của cơ hội mới và AM của cơ hội trùng khác TTKD: hệ thống đi theo quy trình duyệt cơ hội trùng khác TTKD."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 · row "Bước 9"`

**Analyst Note:** Tương tự SC-CH-004 nhưng khác TTKD → routing khác. C-CH-004. Test verify routing đúng luồng khác TTKD.

---

##### SC-CH-006 — Tạo CĐ với KH mới

**Source Quote:**
> "Bước 2: Nếu KH chưa có trong CSDL: chuyển đến bước 4
> Bước 4: Người dùng nhập thông tin còn thiếu và chọn Tạo để tạo cơ hội. Trường hợp thông tin KH chưa tồn tại trong hệ thống: chuyển đến bước 5
> Bước 5: Hệ thống tạo KHTN đồng thời với tạo cơ hội và kết thúc quy trình."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 · rows "Bước 2", "Bước 4", "Bước 5"`

**Analyst Note:** Atomic transaction: KHTN và CĐ được tạo cùng lúc. Test verify: sau submit, cả KHTN mới VÀ CĐ đều tồn tại trong hệ thống. Wireframe cho thấy nhiều loại KH mới (Tổ chức, Cá nhân, Hộ KD, Nước ngoài) → C-CH-001.

---

##### SC-CH-013 — Danh sách CĐ theo tiến trình

**Source Quote:**
> "Màn hình hiển thị tập trung các cơ hội được phân bổ theo tiến trình cơ hội (từ giai đoạn Khai thác cơ hội, review HĐ, Tạo hợp đồng, Triển khai, Xuất hóa đơn, Kết thúc) hỗ trợ người dùng tìm kiếm cơ hội với bộ lọc nâng cao và tính năng xuất Excel."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Danh sách cơ hội"`

**Analyst Note:** 6 giai đoạn tiến trình rõ ràng. Test verify: có 6 tab/group, CĐ phân đúng giai đoạn. Column spec của danh sách chưa có.

---

### PDC — Phê duyệt cơ hội

| Scenario ID | Feature | Req ID | DOC Source | Given | When | Then | Priority | Test Type | Lifecycle |
|-------------|---------|--------|-----------|-------|------|------|----------|-----------|-----------|
| SC-PDC-001 | Phê duyệt CĐ (DT ≤ 300M) | REQ-PDC-001 | DOC-v2.0-01 | TPP/BGĐ TTKD đăng nhập, có CĐ mới chờ phê duyệt với DT kỳ vọng ≤ 300M | TPP/BGĐ TTKD mở CĐ chờ duyệt, review và phê duyệt | CĐ được active, trạng thái chuyển sang bước tiếp theo; notification gửi AM | P1 | Functional | NEW |
| SC-PDC-002 | Phân luồng phê duyệt theo DT > 300M | REQ-PDC-001 | DOC-v2.0-01 | CĐ mới tạo với DT kỳ vọng > 300M | Hệ thống xử lý sau tạo CĐ | Hệ thống tự động routing CĐ đến cấp duyệt cao hơn (theo mốc 300M) | P1 | Functional | NEW |
| SC-PDC-003 | Phê duyệt báo giá vượt hạn mức | REQ-PDC-002 | DOC-v2.0-01 | BGĐ TTKD đăng nhập, có báo giá vượt hạn mức chờ duyệt | BGĐ TTKD review báo giá và phê duyệt/từ chối | Báo giá được approve/reject; AM nhận notification kết quả | P1 | Functional | NEW |
| SC-PDC-004 | TPKT phê duyệt giải pháp → enable Tạo dự án | REQ-PDC-003 | DOC-v2.0-01 | TPKT được phân công review giải pháp của CĐ Tư vấn/Đấu thầu/Triển khai | TPKT xem và phê duyệt giải pháp | Giải pháp được approve; nút "Tạo dự án" enable cho AM; AM có thể tiến hành trên FPMS | P1 | Functional | NEW |
| SC-PDC-005 | TPKT từ chối giải pháp → AM gửi lại | REQ-PDC-003 | DOC-v2.0-01 | TPKT đang review giải pháp | TPKT từ chối giải pháp | AM nhận notification từ chối; AM có thể chỉnh sửa và gửi lại yêu cầu phê duyệt | P2 | Functional | NEW |

#### Source Detail per Scenario — PDC

##### SC-PDC-001 — Phê duyệt CĐ (DT ≤ 300M)

**Source Quote:**
> "Cho phép TPP/BGĐ TTKD đánh giá & phê duyệt cơ hội mới tạo, trước khi cơ hội được active để triển khai.
> Hệ thống tự động phân luồng theo doanh thu kỳ vọng (mốc 300M) và check cơ hội trùng"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Phê duyệt yêu cầu"`

**Analyst Note:** Mốc phân luồng = 300M. Spec không nêu rõ DT ≤ 300M thì TPP duyệt hay BGĐ TTKD duyệt → pending C-PDC-001. Test at high-level: verify CĐ được active sau phê duyệt.

---

##### SC-PDC-004 — TPKT phê duyệt giải pháp → enable Tạo dự án

**Source Quote:**
> "Sau khi giải pháp được phê duyệt, AM sẽ được kích hoạt (enable) nút Tạo dự án để tiến hành các bước tiếp theo trên hệ thống FPMS.
> Hệ thống tự động phân công yêu cầu phê duyệt đến TPKT tương ứng dựa trên Loại dịch vụ và Vùng miền triển khai của cơ hội."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Phê duyệt giải pháp"`

**Analyst Note:** 2 flows: (1) phân công tự động TPKT theo DV + Vùng miền, (2) sau approve → button Tạo dự án enable trên UI. Integration với FPMS external. Test boundary: trước approve → button disable; sau approve → enable.

---

### BC — Báo cáo

| Scenario ID | Feature | Req ID | DOC Source | Given | When | Then | Priority | Test Type | Lifecycle |
|-------------|---------|--------|-----------|-------|------|------|----------|-----------|-----------|
| SC-BC-001 | 7 loại báo cáo cơ hội | REQ-BC-001 | DOC-v2.0-01 | User có quyền truy cập Báo cáo | User vào module Báo cáo cơ hội | Hiển thị đủ 7 loại: BC CĐ mới, BC theo NVKD, BC CĐ thành công, BC CĐ không thành công, BC giai đoạn dự kiến, BC CĐ quá hạn, BC kỹ thuật | P2 | Functional | NEW |
| SC-BC-002 | Báo cáo doanh thu gia hạn | REQ-BC-002 | DOC-v2.0-01 | User có quyền Báo cáo, có HĐ/PL sắp hết hạn | User vào Báo cáo doanh thu gia hạn | Hiển thị danh sách HĐ/PL sắp hết hạn theo 3 mốc: 60 ngày, 30 ngày, 15 ngày | P2 | Functional | NEW |
| SC-BC-003 | Tra cứu báo giá theo Document ID | REQ-BC-003 | DOC-v2.0-01 | User có quyền Tra cứu báo giá | User nhập Document ID hợp lệ vào ô tra cứu | Hiển thị đầy đủ thông tin log liên quan đến lần download báo giá đó | P2 | Functional | NEW |
| SC-BC-004 | Báo cáo Lead | REQ-BC-004 | DOC-v2.0-01 | User có quyền Báo cáo Lead | User vào module Báo cáo Lead | Hiển thị 3 báo cáo: BC Lead thành công, BC Lead thất bại, BC doanh thu hàng tháng | P3 | Functional | NEW |

#### Source Detail per Scenario — BC

##### SC-BC-002 — Báo cáo doanh thu gia hạn

**Source Quote:**
> "Hiển thị danh sách các HĐ/PL sắp hết hạn trong các mốc thời gian 60 ngày, 30 ngày, 15 ngày
> Hỗ trợ sale gia hạn hợp đồng"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Báo cáo doanh thu gia hạn"`

**Analyst Note:** 3 mốc thời gian = từ ngày hiện tại đến ngày hết hạn HĐ/PL ≤ 60/30/15 ngày. Boundary test: HĐ hết hạn đúng 60 ngày (in), 61 ngày (out). Column chi tiết của báo cáo chưa có spec.

---

### CD — Cài đặt & Cấu hình

| Scenario ID | Feature | Req ID | DOC Source | Given | When | Then | Priority | Test Type | Lifecycle |
|-------------|---------|--------|-----------|-------|------|------|----------|-----------|-----------|
| SC-CD-001 | Thiết lập hạn mức báo giá | REQ-CD-001 | DOC-v2.0-01 | QA đăng nhập, vào module Cài đặt | QA nhập hạn mức phê duyệt báo giá cho từng loại dịch vụ và save | Hạn mức được lưu thành công; báo giá vượt hạn mức đó sẽ được routing đến BGĐ TTKD phê duyệt | P2 | Functional | NEW |
| SC-CD-002 | Thiết lập tiêu chí đánh giá | REQ-CD-002 | DOC-v2.0-01 | QA đăng nhập, vào module Cài đặt | QA tạo/cập nhật tiêu chí đánh giá cơ hội và save | Tiêu chí được lưu; TPP/BGĐ TTKD thấy tiêu chí khi phê duyệt CĐ | P2 | Functional | NEW |
| SC-CD-003 | Notification real-time | REQ-CD-003 | DOC-v2.0-01 | User đăng nhập, có notification mới (vd: CĐ được phê duyệt) | Hệ thống phát sinh event tạo notification | Icon chuông 🔔 hiển thị badge số lượng chưa đọc; user click chuông thấy danh sách; có thể lọc đã/chưa đọc; click vào navigate đúng màn hình | P2 | Functional | NEW |
| SC-CD-004 | Email tổng hợp công việc định kỳ | REQ-CD-004 | DOC-v2.0-01 | Đến lịch gửi email định kỳ, có công việc chờ xử lý | Hệ thống chạy scheduled job gửi email | BGĐ Khối/BGĐ TTKD/TP/NVKD nhận email tổng hợp với danh sách công việc + hyperlink điều hướng | P3 | Functional | NEW |

#### Source Detail per Scenario — CD

##### SC-CD-003 — Notification real-time

**Source Quote:**
> "Hệ thống gửi thông báo real-time tới user qua icon chuông (🔔) trên header. User có thể xem danh sách thông báo, lọc theo trạng thái đã đọc/chưa đọc, mark all as read và click vào thông báo để điều hướng tới màn hình tương ứng."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Notification"`

**Analyst Note:** 4 user actions: xem list, lọc đã/chưa đọc, mark all read, click → điều hướng. Real-time = không cần F5. Loại event nào trigger notification chưa có spec → C-CD-001.

---

### KH — Khách hàng / Lead / Công việc / Đơn hàng

| Scenario ID | Feature | Req ID | DOC Source | Given | When | Then | Priority | Test Type | Lifecycle |
|-------------|---------|--------|-----------|-------|------|------|----------|-----------|-----------|
| SC-KH-001 | Tạo mới KH cá nhân/doanh nghiệp | REQ-KH-001 | DOC-v2.0-01 | User có quyền quản lý KH | User nhập thông tin KH mới (cá nhân hoặc DN) và save | KH mới được tạo trong hệ thống; có thể tra cứu và sử dụng cho Cơ hội | P2 | Functional | NEW |
| SC-KH-002 | Tra cứu KH theo tên/MST | REQ-KH-001 | DOC-v2.0-01 | Đang ở màn hình Khách hàng | User nhập tên hoặc MST tìm kiếm | Hệ thống trả về danh sách KH khớp tìm kiếm | P2 | Functional | NEW |
| SC-KH-003 | Cập nhật thông tin KH | REQ-KH-001 | DOC-v2.0-01 | User có quyền, KH đã tồn tại trong hệ thống | User chỉnh sửa thông tin KH và save | Thông tin KH được cập nhật; lịch sử tương tác ghi nhận thay đổi | P2 | Functional | NEW |
| SC-KH-004 | Xem Lead từ CRM/FTEL | REQ-KH-002 | DOC-v2.0-01 | Hệ thống đã đồng bộ Lead từ CRM/FTEL | User vào module Lead | Danh sách Lead đồng bộ từ CRM/FTEL hiển thị với thông tin KHTN | P2 | Functional | NEW |
| SC-KH-005 | Tạo Công việc liên quan cơ hội | REQ-KH-003 | DOC-v2.0-01 | User đang ở màn hình chi tiết CĐ hoặc module Công việc | User tạo công việc mới gán cho cá nhân/nhóm với deadline và mức độ ưu tiên | Công việc được tạo, xuất hiện trong danh sách công việc; người được giao nhận notification | P2 | Functional | NEW |
| SC-KH-006 | Xem chi tiết Đơn hàng | REQ-KH-004 | DOC-v2.0-01 | User có quyền xem Đơn hàng | User mở màn hình Đơn hàng của đối tác | Hiển thị đầy đủ: thông tin đơn hàng, KH, DV (chi tiết triển khai, liên hệ triển khai, liên hệ thu cước), thanh toán, timeline, khung comment | P3 | Functional | NEW |

#### Source Detail per Scenario — KH

##### SC-KH-004 — Xem Lead từ CRM/FTEL

**Source Quote:**
> "Lưu trữ, theo dõi và đánh giá chuyển đổi thông tin khách hàng tiềm năng được đồng bộ từ hệ thống CRM của FTEL"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Lead"`

**Analyst Note:** Lead được đồng bộ từ CRM FTEL (external system). Test verify: data sync hoạt động; thông tin Lead hiển thị đúng. Cơ chế sync (real-time hay batch) và field mapping chưa có spec.

---

##### SC-KH-006 — Xem chi tiết Đơn hàng

**Source Quote:**
> "Màn hình hiển thị chi tiết đơn hàng đối tác mà người dùng muốn xem. Hiển thị đầy đủ thông tin: thông tin đơn hàng, thông tin khách hàng, thông tin dịch vụ (chi tiết triển khai, liên hệ triển khai, liên hệ thu cước), thông tin thanh toán, trạng thái đơn hàng (timeline) và khung trao đổi/comment."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Đơn hàng"`

**Analyst Note:** View-only (không CRUD). 6 sections rõ ràng. Test verify tất cả 6 sections hiển thị đủ fields. Source data từ hệ thống đối tác (không rõ source).

---

## Scenarios — CARRIED (reference only)

*(Không có — v2.0 là version đầu tiên)*

## Scenarios — DEPRECATED

*(Không có — v2.0 là version đầu tiên)*
