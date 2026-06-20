# MEMORY — Analyze Requirements Output — v2.0

> Tạo bởi: skill analyze-requirements
> Cập nhật lần cuối: 2026-06-14 — INIT analysis
> Parent version: — (version đầu tiên)

## 0. Version Context

- **Version:** v2.0
- **Parent:** — (initial version)
- **Delta type:** Major (initial)
- **Input folder:** 00_input/v2.0/
- **Shared docs applied:** Không
- **Analysis mode:** INIT

## 1. Project Overview

- **Dự án:** FTI BMS v2.0 (Business Management System)
- **Mô tả:** Hệ thống quản lý nghiệp vụ kinh doanh của FTI, phiên bản 2.0 nâng cấp từ v1.7. Tối ưu cấu trúc lưu trữ, chuẩn hóa UX/UI, bổ sung cảnh báo nghiệp vụ, xây dựng nền tảng đo lường SLA và FPA.
- **Môi trường:** STG — URL: TBD

## 2. Document Registry (version-scoped)

| DOC ID | File | Loại | Ngày phân tích | Status | Modules liên quan |
|--------|------|------|---------------|--------|-------------------|
| DOC-v2.0-01 | ISC_FTI-BMS_V2.0_URD_1.0_final.docx | URD | 2026-06-14 | Analyzed | DASH, CH, PDC, BC, CD, KH |

## 3. Module Summary

| Module | DOC Source | Tổng Req | Tổng SC | NEW | MODIFIED | CARRIED | DEPRECATED | P1 | P2 | P3 | Risk Level |
|--------|-----------|----------|---------|-----|----------|---------|-----------|----|----|----|-----------:|
| DASH (Dashboard) | DOC-v2.0-01 | 7 | 6 | 6 | 0 | 0 | 0 | 2 | 3 | 1 | Medium |
| CH (Cơ hội) | DOC-v2.0-01 | 12 | 15 | 15 | 0 | 0 | 0 | 6 | 8 | 1 | High |
| PDC (Phê duyệt cơ hội) | DOC-v2.0-01 | 7 | 5 | 5 | 0 | 0 | 0 | 4 | 1 | 0 | High |
| BC (Báo cáo) | DOC-v2.0-01 | 4 | 4 | 4 | 0 | 0 | 0 | 0 | 3 | 1 | Low |
| CD (Cài đặt & Cấu hình) | DOC-v2.0-01 | 5 | 4 | 4 | 0 | 0 | 0 | 0 | 3 | 1 | Medium |
| KH (Khách hàng/Lead/CV/DH) | DOC-v2.0-01 | 6 | 6 | 6 | 0 | 0 | 0 | 0 | 5 | 1 | Low |
| **TỔNG** | | **41** | **40** | **40** | **0** | **0** | **0** | **12** | **23** | **5** | |

## 4. Scenario Index

| SC ID | Tên ngắn | Module | DOC Source | Priority | Test Type | Lifecycle | TC Status | Vibe Status | Vibe Date |
|-------|----------|--------|-----------|----------|-----------|-----------|-----------|-------------|-----------|
| SC-DASH-001 | Dashboard auto-display sau login | DASH | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-DASH-002 | KPI stats hiển thị đầy đủ theo phân quyền | DASH | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-DASH-003 | Click menu Dashboard → hiển thị | DASH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-DASH-004 | Biểu đồ & chart hiển thị đúng dữ liệu | DASH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-DASH-005 | Top 5 cơ hội + Lý do đóng cơ hội | DASH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-DASH-006 | Tương tác widget (lọc, drill-down) | DASH | DOC-v2.0-01 | P3 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-001 | Tạo CĐ - KH cũ, không có CĐ đang mở | CH | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-002 | Tạo CĐ - KH cũ, CĐ đang mở, khác DV | CH | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-003 | Tạo CĐ - cùng DV, cùng AM → thành công | CH | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-004 | Tạo CĐ - cùng DV, khác AM, cùng TTKD | CH | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-005 | Tạo CĐ - cùng DV, khác AM, khác TTKD | CH | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-006 | Tạo CĐ - KH mới → tạo KHTN + CĐ đồng thời | CH | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-007 | Tìm kiếm KH bằng MST | CH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-008 | Tìm kiếm KH bằng tên | CH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-009 | Bỏ trống trường bắt buộc → validation error | CH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-010 | User không có quyền Tạo cơ hội → từ chối | CH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-011 | Notification gửi Sale Manager sau tạo CĐ | CH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-012 | CĐ tạo xong → xuất hiện danh sách status "Mới" | CH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-013 | Danh sách CĐ hiển thị theo tiến trình | CH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-014 | Tìm kiếm/lọc nâng cao danh sách CĐ | CH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CH-015 | Xuất danh sách CĐ ra Excel | CH | DOC-v2.0-01 | P3 | Functional | NEW | ⏳ | ⏳ | — |
| SC-PDC-001 | TPP/BGĐ TTKD phê duyệt CĐ (DT ≤ 300M) | PDC | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-PDC-002 | Phân luồng phê duyệt theo DT kỳ vọng (> 300M) | PDC | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-PDC-003 | BGĐ TTKD phê duyệt/từ chối báo giá vượt hạn mức | PDC | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-PDC-004 | TPKT phê duyệt giải pháp → enable Tạo dự án | PDC | DOC-v2.0-01 | P1 | Functional | NEW | ⏳ | ⏳ | — |
| SC-PDC-005 | TPKT từ chối giải pháp → AM chỉnh sửa, gửi lại | PDC | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-BC-001 | Hiển thị 7 loại Báo cáo cơ hội | BC | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-BC-002 | Báo cáo doanh thu gia hạn (60/30/15 ngày) | BC | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-BC-003 | Tra cứu báo giá bằng Document ID | BC | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-BC-004 | Báo cáo Lead (thành công/thất bại/DT tháng) | BC | DOC-v2.0-01 | P3 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CD-001 | QA thiết lập hạn mức phê duyệt báo giá | CD | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CD-002 | QA thiết lập tiêu chí đánh giá cơ hội | CD | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CD-003 | Notification real-time qua icon chuông | CD | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-CD-004 | Hệ thống gửi email công việc định kỳ | CD | DOC-v2.0-01 | P3 | Functional | NEW | ⏳ | ⏳ | — |
| SC-KH-001 | Tạo mới khách hàng (cá nhân/doanh nghiệp) | KH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-KH-002 | Tra cứu/tìm kiếm khách hàng | KH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-KH-003 | Cập nhật thông tin khách hàng | KH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-KH-004 | Xem Lead đồng bộ từ CRM/FTEL | KH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-KH-005 | Tạo/theo dõi Công việc liên quan cơ hội | KH | DOC-v2.0-01 | P2 | Functional | NEW | ⏳ | ⏳ | — |
| SC-KH-006 | Xem chi tiết Đơn hàng đối tác | KH | DOC-v2.0-01 | P3 | Functional | NEW | ⏳ | ⏳ | — |

### 4.1. Source Detail (verbatim quotes)

#### REQ-DASH-001 — Dashboard auto-display sau login

**Source Quote:**
> "Trigger: Người dùng đăng nhập hệ thống thành công hoặc click vào menu "Dashboard"."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §DASHBOARD · Table 5 (Use Case) · row "Trigger"`

**Analyst Note:** Dashboard là màn hình mặc định hiển thị sau khi login thành công. Cũng có thể trigger bằng click menu. Implicit: nếu user đã đăng nhập và truy cập URL hệ thống, Dashboard là trang đích đầu tiên.

---

#### REQ-DASH-002 — KPI stats hiển thị theo phân quyền

**Source Quote:**
> "Màn hình Dashboard cung cấp cái nhìn tổng quan về tình trạng hoạt động của hệ thống FTI BMS, bao gồm các chỉ số:
> Thống kê: Khách hàng tiềm năng mới. Cơ hội mới, Cơ hội chờ duyệt, Doanh thu dự kiến, Tỷ lệ cơ hội thành công
> Nhóm dịch vụ phổ biến
> Cơ hội theo thời gian
> Trạng thái cơ hội
> Doanh thu theo nhóm dịch vụ
> Top 5 cơ hội có doanh thu dự kiến cao nhất
> Lý do đóng cơ hội"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §DASHBOARD · Table 5 · row "Description"`

**Analyst Note:** 9 loại widget/biểu đồ. Dữ liệu filter theo phân quyền (row "Actor": "Theo ma trận phân quyền sẽ xem được các dữ liệu tương ứng"). Ma trận phân quyền chưa accessible → C-DASH-001.

---

#### REQ-DASH-003 — Pre/Post conditions Dashboard

**Source Quote:**
> "Pre-Conditions: Người dùng đã đăng nhập hệ thống thành công
> Có quyền truy cập Dashboard
> Dữ liệu đã được đồng bộ/tính toán từ hệ thống backend
> Post-Conditions: Hiển thị các widget/biểu đồ/tổng hợp dữ liệu theo quyền user
> Người dùng có thể tương tác (lọc, xem chi tiết)"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §DASHBOARD · Table 5 · rows "Pre-Conditions" + "Post-Conditions"`

**Analyst Note:** Điều kiện tiên quyết: login + có quyền + dữ liệu đã sync từ backend. Implicit: cần handle trường hợp dữ liệu chưa sync (loading state / empty state). Liên quan C-DASH-002.

---

#### REQ-CH-001 — Tạo cơ hội - Use Case description

**Source Quote:**
> "Cho phép nhân viên kinh doanh (Sale) tạo mới một cơ hội kinh doanh trong hệ thống BMS, nhập đầy đủ thông tin về khách hàng, sản phẩm/dịch vụ, giá trị, giai đoạn và người phụ trách."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 6 · row "Description"`

**Analyst Note:** Actor chính là Sale (AM). Có cả TPKD/BGĐ TTKD/BGĐ KHỐI/Admin (từ Table 7). Form gồm: thông tin cơ hội, khách hàng, sản phẩm/DV, giá trị, giai đoạn, người phụ trách. Wireframe không readable từ .docx → C-CH-001 (danh sách field bắt buộc).

---

#### REQ-CH-002 — Trigger + Pre-Conditions Tạo cơ hội

**Source Quote:**
> "Trigger: Click vào menu Cơ hội >> Tạo cơ hội
> Pre-Conditions: Người dùng đã đăng nhập và có quyền "Tạo cơ hội"
> Dữ liệu khách hàng đã tồn tại trong hệ thống hoặc có thể tạo mới"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 6 · rows "Trigger" + "Pre-Conditions"`

**Analyst Note:** User phải có permission "Tạo cơ hội". KH có thể là existing (tìm kiếm) hoặc new (tạo mới). Quyền "Tạo cơ hội" chi tiết theo ma trận phân quyền → C-DASH-001.

---

#### REQ-CH-003 — Post-Conditions Tạo cơ hội

**Source Quote:**
> "Post-Conditions: Cơ hội mới được tạo với trạng thái "Mới" hoặc stage được chọn • Hệ thống gửi notification đến Sale Manager • Cơ hội xuất hiện trong Danh sách cơ hội"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 6 · row "Post-Conditions"`

**Analyst Note:** 3 kết quả sau tạo cơ hội: (1) status = "Mới" hoặc stage được chọn, (2) notification → Sale Manager, (3) xuất hiện trong danh sách. Implicit: có thể chọn stage khác "Mới" khi tạo.

---

#### REQ-CH-004 — Workflow Tạo cơ hội (9 bước)

**Source Quote:**
> "Bước 1: Người dùng chọn tạo cơ hội, nhập thông tin cơ hội, nhập MST hoặc tên khách hàng để tìm kiếm thông tin khách hàng.
> Bước 2: Hệ thống tìm kiếm khách hàng bằng MST/tên khách hàng: Nếu KH đã có trong CSDL: chuyển đến bước 3. Nếu KH chưa có trong CSDL: chuyển đến bước 4.
> Bước 3: Hệ thống tự động điền thông tin KH bằng thông tin đã lưu trong CSDL.
> Bước 4: Người dùng nhập thông tin còn thiếu và chọn Tạo để tạo cơ hội. Trường hợp thông tin KH đã tồn tại trong hệ thống: chuyển đến bước 6. Trường hợp thông tin KH chưa tồn tại trong hệ thống: chuyển đến bước 5.
> Bước 5: Hệ thống tạo KHTN đồng thời với tạo cơ hội và kết thúc quy trình.
> Bước 6: Hệ thống check nếu KH đang có cơ hội ĐANG MỞ: Nếu có: chuyển đến bước 7. Nếu không: hệ thống tạo cơ hội và hoàn tất quy trình.
> Bước 7: Hệ thống check nếu loại dịch vụ của cơ hội được tạo trùng với loại dịch vụ của cơ hội đang mở của khách hàng: Nếu trùng: chuyển đến bước 8. Nếu không: hệ thống tạo cơ hội và hoàn tất quy trình.
> Bước 8: Hệ thống kiểm tra AM của cơ hội: Nếu AM của cơ hội mới đồng thời là AM của cơ hội trùng: hệ thống tạo cơ hội và hoàn tất quy trình. Nếu AM của cơ hội mới không phải là AM của cơ hội trùng: hệ thống kiểm tra điều kiện 9.
> Bước 9: Hệ thống kiểm tra TTKD của AM: Nếu AM của cơ hội mới và AM của cơ hội trùng cùng TTKD: hệ thống đi theo quy trình duyệt cơ hội trùng cùng TTKD. Nếu AM của cơ hội mới và AM của cơ hội trùng khác TTKD: hệ thống đi theo quy trình duyệt cơ hội trùng khác TTKD."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 · rows 1-9`

**Analyst Note:** Workflow phức tạp với 5 luồng chính từ 9 bước điều kiện. Quy trình duyệt cơ hội trùng (cùng TTKD / khác TTKD) chưa được đặc tả chi tiết trong URD → C-CH-003, C-CH-004. Bước 3 (Chọn người phê duyệt) trong wireframe (para [80]) cũng cần clarification → C-CH-002.

---

#### REQ-PDC-001 — Phê duyệt yêu cầu cơ hội

**Source Quote:**
> "Cho phép TPP/BGĐ TTKD đánh giá & phê duyệt cơ hội mới tạo, trước khi cơ hội được active để triển khai.
> Hệ thống tự động phân luồng theo doanh thu kỳ vọng (mốc 300M) và check cơ hội trùng"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Phê duyệt yêu cầu"`

**Analyst Note:** 2 yếu tố phân luồng: (1) doanh thu kỳ vọng theo mốc 300M, (2) check cơ hội trùng. Chi tiết luồng phê duyệt chưa có spec → C-PDC-001.

---

#### REQ-PDC-002 — Phê duyệt báo giá

**Source Quote:**
> "Tính năng cho phép Ban Giám đốc (BGĐ) Trung tâm Kinh doanh thực hiện thẩm định, phê duyệt hoặc từ chối các yêu cầu báo giá do nhân viên kinh doanh (AM) khởi tạo
> Hệ thống sẽ phân loại các báo giá vượt hạn mức quy định (được thiết lập trong phần Cài đặt) để gửi đến cấp quản lý phê duyệt nhằm đảm bảo tính chính xác và kiểm soát giá trị kinh doanh trước khi gửi cho khách hàng"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Phê duyệt báo giá"`

**Analyst Note:** Hạn mức báo giá được cấu hình trong module Cài đặt (SC-CD-001). Báo giá vượt hạn mức → tự động routing đến BGĐ TTKD. Liên quan CD module.

---

#### REQ-PDC-003 — Phê duyệt giải pháp kỹ thuật

**Source Quote:**
> "Chức năng cho phép Trưởng phòng Kỹ thuật (TPKT) phê duyệt hoặc từ chối giải pháp kỹ thuật cho cơ hội kinh doanh có yêu cầu tạo dự án (Tư vấn/Đấu thầu hoặc Triển khai).
> Hệ thống tự động phân công yêu cầu phê duyệt đến TPKT tương ứng dựa trên Loại dịch vụ và Vùng miền triển khai của cơ hội.
> Sau khi giải pháp được phê duyệt, AM sẽ được kích hoạt (enable) nút Tạo dự án để tiến hành các bước tiếp theo trên hệ thống FPMS.
> Trường hợp giải pháp bị từ chối, AM có thể chỉnh sửa và gửi lại yêu cầu phê duyệt."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Phê duyệt giải pháp"`

**Analyst Note:** TPKT được phân công tự động theo Loại DV + Vùng miền. Approve → enable button Tạo dự án (FPMS). Từ chối → AM có thể sửa và gửi lại (không giới hạn số lần).

---

#### REQ-BC-001 — Báo cáo cơ hội (7 loại)

**Source Quote:**
> "Hiển thị danh sách báo cáo, bao gồm:
> Báo cáo cơ hội mới
> Báo cáo theo NVKD
> Báo cáo cơ hội thành công
> Báo cáo cơ hội không thành công
> Báo cáo giai đoạn dự kiến
> Báo cáo cơ hội quá hạn
> Báo cáo kỹ thuật"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Báo cáo cơ hội"`

**Analyst Note:** 7 loại báo cáo cơ hội. Columns/filters của từng báo cáo chưa được đặc tả → C-BC-001.

---

#### REQ-BC-002 — Báo cáo doanh thu gia hạn

**Source Quote:**
> "Hiển thị danh sách các HĐ/PL sắp hết hạn trong các mốc thời gian 60 ngày, 30 ngày, 15 ngày
> Hỗ trợ sale gia hạn hợp đồng"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Báo cáo doanh thu gia hạn"`

**Analyst Note:** 3 mốc thời gian: 60/30/15 ngày trước ngày hết hạn HĐ/PL. Mục tiêu: nhắc sale gia hạn. Chi tiết columns chưa có spec.

---

#### REQ-CD-001 — Notification real-time

**Source Quote:**
> "Hệ thống gửi thông báo real-time tới user qua icon chuông (🔔) trên header. User có thể xem danh sách thông báo, lọc theo trạng thái đã đọc/chưa đọc, mark all as read và click vào thông báo để điều hướng tới màn hình tương ứng."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Notification"`

**Analyst Note:** Icon chuông trên header. 4 thao tác user: xem list, lọc đã đọc/chưa đọc, mark all read, click điều hướng. Loại trigger notification chưa được liệt kê đầy đủ (ẩn hiện qua UX) → C-CD-001.

---

#### REQ-KH-001 — Quản lý Khách hàng

**Source Quote:**
> "Chức năng cho phép người dùng quản lý toàn bộ thông tin khách hàng (cá nhân/doanh nghiệp) trên hệ thống, bao gồm tạo mới, cập nhật, tra cứu và theo dõi lịch sử tương tác. Dữ liệu khách hàng là nguồn đầu vào xuyên suốt cho các nghiệp vụ như Cơ hội, Báo giá, Hợp đồng (HĐ/PL) và Chăm sóc khách hàng."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 · row "Khách hàng"`

**Analyst Note:** CRUD khách hàng (cá nhân + doanh nghiệp) + lịch sử tương tác. KH là master data dùng chung cho Cơ hội, Báo giá, HĐ/PL. Chi tiết form KH chưa có spec.

---

## 5. Test Data Summary

| Module | DOC Source | Fields chính | Số bộ valid | Số bộ invalid | Có boundary? |
|--------|-----------|-------------|-------------|---------------|-------------|
| DASH | DOC-v2.0-01 | User role, permission, data sync | 2 | 2 | Không |
| CH (Tạo CĐ) | DOC-v2.0-01 | MST, tên KH, loại DV, AM, TTKD, doanh thu | 5 | 3 | Có (mốc 300M) |
| PDC | DOC-v2.0-01 | Doanh thu kỳ vọng (mốc 300M), hạn mức báo giá | 2 | 2 | Có (300M, hạn mức) |
| BC | DOC-v2.0-01 | Ngày hết hạn HĐ/PL, Document ID | 2 | 1 | Có (60/30/15 ngày) |
| CD | DOC-v2.0-01 | Hạn mức báo giá (giá trị tiền), tiêu chí đánh giá | 2 | 1 | Có (giá trị hạn mức) |
| KH | DOC-v2.0-01 | MST, tên KH, loại KH (cá nhân/DN) | 3 | 2 | Không |

## 6. Clarifications & Blockers

| # | Req ID | DOC Source | Vấn đề | Answer | Status | Ngày resolve | Ảnh hưởng |
|---|--------|-----------|--------|--------|--------|-------------|-----------|
| C-DASH-001 | REQ-DASH-002, REQ-CH-002 | DOC-v2.0-01 | Ma trận phân quyền: "theo link" — external link không accessible. Không biết role nào thấy widget nào, thực hiện action nào | — | Open | — | BLOCKER cho nhiều SC (DASH, CH, PDC) |
| C-DASH-002 | REQ-DASH-003 | DOC-v2.0-01 | "Dữ liệu đã được đồng bộ/tính toán từ hệ thống backend" — không có spec về loading state, empty state, lỗi backend | — | Open | — | Non-blocking |
| C-CH-001 | REQ-CH-001 | DOC-v2.0-01 | Form Tạo cơ hội: wireframe ảnh (.docx) không đọc được. Không biết field nào bắt buộc/không bắt buộc, validation rule cho từng field | — | Open | — | BLOCKER cho SC-CH-009 |
| C-CH-002 | REQ-CH-004 | DOC-v2.0-01 | "Bước 3: Chọn người phê duyệt" (para [80] URD) — chi tiết không có trong URD. Ai được chọn? Tự động hay manual? | — | Open | — | BLOCKER cho SC-CH-013 |
| C-CH-003 | REQ-CH-004 | DOC-v2.0-01 | "Quy trình duyệt cơ hội trùng cùng TTKD" — không được đặc tả trong URD v2.0 | — | Open | — | BLOCKER cho SC-CH-004 |
| C-CH-004 | REQ-CH-004 | DOC-v2.0-01 | "Quy trình duyệt cơ hội trùng khác TTKD" — không được đặc tả trong URD v2.0 | — | Open | — | BLOCKER cho SC-CH-005 |
| C-PDC-001 | REQ-PDC-001 | DOC-v2.0-01 | Chi tiết luồng phê duyệt cơ hội (màn hình, action, condition) chưa có đặc tả riêng trong URD | — | Open | — | Non-blocking (high-level test được) |
| C-BC-001 | REQ-BC-001 | DOC-v2.0-01 | 7 loại báo cáo cơ hội: chỉ có tên, không có spec về columns, filters, export | — | Open | — | Non-blocking (high-level test được) |
| C-CD-001 | REQ-CD-001 | DOC-v2.0-01 | Notification: không rõ loại events nào trigger notification (tạo CĐ? phê duyệt? deadline?) | — | Open | — | Non-blocking |

### 6.1. Clarification Source Detail

#### C-DASH-001 — Ma trận phân quyền không accessible

**Source Quote (ambiguous):**
> "Ma trận phân quyền: theo link"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · paragraph trước bảng spec · line "Ma trận phân quyền: theo link"`

**Analyst Note:** URD tham chiếu external link cho ma trận phân quyền nhưng không embed trong doc. Cần BA/PM cung cấp file phân quyền. BLOCKER: không biết actor nào có thể làm gì → SC liên quan đến permission sẽ có Given "user có quyền X" mà không verify được quyền X là role nào.

---

#### C-CH-001 — Field validation form Tạo cơ hội

**Source Quote (ambiguous):**
> "nhập đầy đủ thông tin về khách hàng, sản phẩm/dịch vụ, giá trị, giai đoạn và người phụ trách"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 6 · row "Description"`

**Analyst Note:** Mô tả general không liệt kê field cụ thể. Wireframe trong URD là ảnh embed không đọc được từ text extraction. Cần BA cung cấp: danh sách field bắt buộc/optional, độ dài max, format validation cho từng field.

---

#### C-CH-003 — Quy trình duyệt CĐ trùng cùng TTKD

**Source Quote (ambiguous):**
> "Nếu AM của cơ hội mới và AM của cơ hội trùng cùng TTKD: hệ thống đi theo quy trình duyệt cơ hội trùng cùng TTKD."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 · row "Bước 9"`

**Analyst Note:** Tham chiếu "quy trình duyệt cơ hội trùng cùng TTKD" nhưng không define quy trình này trong URD v2.0. Cần BA cung cấp flow diagram hoặc spec bổ sung. BLOCKER cho SC-CH-004.

---

## 7. Automation Context

- **Framework:** Playwright TypeScript
- **POM path:** `10_source-code/pages/`
- **Naming convention:** Chưa xác định (chạy scan-source-code sau khi có source)

## 8. Deliverable Files Reference

| File | Đường dẫn | Mô tả |
|------|-----------|-------|
| Requirement Traceability | `02_analyze-requirements/v2.0/requirement_traceability.md` | Ma trận truy vết |
| Test Scenario Map | `02_analyze-requirements/v2.0/test_scenario_map.md` | Chi tiết scenarios |
| Test Data Catalog | `02_analyze-requirements/v2.0/test_data_catalog.md` | Dữ liệu test |
| Risk Assessment | `02_analyze-requirements/v2.0/risk_assessment.md` | Đánh giá rủi ro |

## 9. TC Generation Log

> Header khớp generate-tc (Mode + Techniques cols, added 2026-05-29).

| DOC ID | Ngày generate | Tổng TC | File output | Priority | Mode | Techniques | Review Status |
|--------|--------------|---------|-------------|----------|------|------------|---------------|
| DOC-v2.0-01 | — | — | — | — | — | — | ⏳ |
