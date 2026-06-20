# Requirement Traceability — v2.0

> Tạo bởi: analyze-requirements. Ma trận truy vết REQ ↔ DOC ↔ Scenario ↔ Clarification.
> Text-level traceability: Source Quote per REQ ở `MEMORY.md §4.1`, per SC ở `test_scenario_map.md`.
> `req_notation: none` — doc không đánh số FR/VR/AC/UC, dùng §section reference.
>
> **Structure-lock:** giữ nguyên header cột + section. KHÔNG tự thêm/bớt/đổi tên cột.

## 1. Traceability Matrix (REQ → DOC → SC)

### Module DASH — Dashboard — DOC-v2.0-01

| REQ ID | Maps (Ref DOC) | DOC §section | Scenarios | Clarification |
|--------|----------------|--------------|-----------|---------------|
| REQ-DASH-001 | — | §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §DASHBOARD · Table 5 "Trigger" | SC-DASH-001, SC-DASH-003 | — |
| REQ-DASH-002 | — | §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §DASHBOARD · Table 5 "Description" | SC-DASH-002, SC-DASH-004, SC-DASH-005 | C-DASH-001 |
| REQ-DASH-003 | — | §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §DASHBOARD · Table 5 "Pre/Post-Conditions" | SC-DASH-002, SC-DASH-006 | C-DASH-002 |

### Module CH — Cơ hội — DOC-v2.0-01

| REQ ID | Maps (Ref DOC) | DOC §section | Scenarios | Clarification |
|--------|----------------|--------------|-----------|---------------|
| REQ-CH-001 | — | §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 6 "Description" | SC-CH-001 đến SC-CH-006, SC-CH-009 | C-CH-001 |
| REQ-CH-002 | — | §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 6 "Trigger" + "Pre-Conditions" | SC-CH-010 | C-DASH-001 |
| REQ-CH-003 | — | §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 6 "Post-Conditions" | SC-CH-011, SC-CH-012 | — |
| REQ-CH-004 | — | §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 (workflow 9 bước) | SC-CH-001 đến SC-CH-008 | C-CH-001, C-CH-002, C-CH-003, C-CH-004 |
| REQ-CH-005 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Danh sách cơ hội" | SC-CH-013, SC-CH-014, SC-CH-015 | — |

### Module PDC — Phê duyệt cơ hội — DOC-v2.0-01

| REQ ID | Maps (Ref DOC) | DOC §section | Scenarios | Clarification |
|--------|----------------|--------------|-----------|---------------|
| REQ-PDC-001 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Phê duyệt yêu cầu" | SC-PDC-001, SC-PDC-002 | C-PDC-001 |
| REQ-PDC-002 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Phê duyệt báo giá" | SC-PDC-003 | — |
| REQ-PDC-003 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Phê duyệt giải pháp" | SC-PDC-004, SC-PDC-005 | — |
| REQ-PDC-004 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Phê duyệt tạo HĐ/PL" | — | C-PDC-001 |
| REQ-PDC-005 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Phê duyệt dự án" | — | C-PDC-001 |

### Module BC — Báo cáo — DOC-v2.0-01

| REQ ID | Maps (Ref DOC) | DOC §section | Scenarios | Clarification |
|--------|----------------|--------------|-----------|---------------|
| REQ-BC-001 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Báo cáo cơ hội" | SC-BC-001 | C-BC-001 |
| REQ-BC-002 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Báo cáo doanh thu gia hạn" | SC-BC-002 | — |
| REQ-BC-003 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Tra cứu báo giá" | SC-BC-003 | — |
| REQ-BC-004 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Báo cáo Lead" | SC-BC-004 | — |

### Module CD — Cài đặt & Cấu hình — DOC-v2.0-01

| REQ ID | Maps (Ref DOC) | DOC §section | Scenarios | Clarification |
|--------|----------------|--------------|-----------|---------------|
| REQ-CD-001 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Thiết lập hạn mức báo giá" | SC-CD-001 | — |
| REQ-CD-002 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Thiết lập tiêu chí đánh giá" | SC-CD-002 | — |
| REQ-CD-003 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Notification" | SC-CD-003 | C-CD-001 |
| REQ-CD-004 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Email" | SC-CD-004 | — |
| REQ-CD-005 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Cấu hình phân bổ Lead" | — | — |

### Module KH — Khách hàng / Lead / CV / DH — DOC-v2.0-01

| REQ ID | Maps (Ref DOC) | DOC §section | Scenarios | Clarification |
|--------|----------------|--------------|-----------|---------------|
| REQ-KH-001 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Khách hàng" | SC-KH-001, SC-KH-002, SC-KH-003 | — |
| REQ-KH-002 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Lead" | SC-KH-004 | — |
| REQ-KH-003 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Công việc" | SC-KH-005 | — |
| REQ-KH-004 | — | §DANH SÁCH CHỨC NĂNG · §Danh sách chức năng · Table 4 "Đơn hàng" | SC-KH-006 | — |

## 2. Coverage Summary

- **Scenario có REQ + DOC source:** 40/40 (100%).
- **REQ có ≥1 scenario:** ~30/37 (~81%). 7 REQ chưa có scenario riêng vì thiếu spec chi tiết.
- **REQ chưa có scenario (gap có chủ đích):** REQ-PDC-004 (Phê duyệt HĐ/PL — pending detail spec), REQ-PDC-005 (Phê duyệt dự án — pending detail spec), REQ-CD-005 (Cấu hình phân bổ Lead — brief desc only), các sub-feature Chi tiết cơ hội, Yêu cầu HĐ/PL — chỉ có mô tả ngắn trong Table 4, chưa đủ để derive scenario.
- **Mốc cập nhật:** Baseline 2026-06-14. Cập nhật sau `/analyze-requirements --update` hoặc `/analyze-requirements --sweep`.

## 3. Clarifications — Source Quote (ambiguous text)

#### C-DASH-001 — Ma trận phân quyền external link (BLOCKER)

**Source Quote (ambiguous):**
> "Ma trận phân quyền: theo link"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · paragraph trước §DASHBOARD spec · line 1`

**Analyst Note:** URD reference link external cho toàn bộ permission matrix. Không có URL hoặc attach file. Ảnh hưởng: actor cho tất cả SC không verify được. BLOCKER cho generate-tc nếu cần test per-role. Proposed resolution: BA cung cấp file phân quyền (Excel/Word).

---

#### C-CH-001 — Form Tạo CĐ — field validation (BLOCKER cho SC-CH-009)

**Source Quote (ambiguous):**
> "nhập đầy đủ thông tin về khách hàng, sản phẩm/dịch vụ, giá trị, giai đoạn và người phụ trách"

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 6 · row "Description"`

**Analyst Note:** "Đầy đủ thông tin" không liệt kê cụ thể field nào required, độ dài max, format validation. Wireframe trong URD là ảnh embed — không extract được text. Cần BA gửi: (1) danh sách field + required/optional, (2) validation rule per field.

---

#### C-CH-003 — Quy trình duyệt CĐ trùng cùng TTKD (BLOCKER cho SC-CH-004)

**Source Quote (ambiguous):**
> "hệ thống đi theo quy trình duyệt cơ hội trùng cùng TTKD."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 · row "Bước 9" · condition 1`

**Analyst Note:** Tham chiếu quy trình không được define trong URD v2.0. Proposed: BA bổ sung spec luồng duyệt CĐ trùng cùng TTKD (màn hình, actor, điều kiện approve/reject, notification).

---

#### C-CH-004 — Quy trình duyệt CĐ trùng khác TTKD (BLOCKER cho SC-CH-005)

**Source Quote (ambiguous):**
> "hệ thống đi theo quy trình duyệt cơ hội trùng khác TTKD."

**Source Location:** `DOC-v2.0-01 §DANH SÁCH CHỨC NĂNG · §Đặc tả chức năng · §TẠO CƠ HỘI · Table 7 · row "Bước 9" · condition 2`

**Analyst Note:** Tương tự C-CH-003 cho case khác TTKD. Cần spec riêng cho luồng này (thường phức tạp hơn vì cross-center).
