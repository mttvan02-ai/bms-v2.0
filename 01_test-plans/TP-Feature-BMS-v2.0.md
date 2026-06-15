# Test Plan: BMS V2.0 — Feature Test Plan

> **Version:** v2.0 · **Loại:** Feature · **Ngày tạo:** 2026-06-14
> **QC phụ trách:** VanMTT3 · **Team:** Solo

---

## 1. Giới thiệu

| Field | Value |
|-------|-------|
| Dự án | BMS V2.0 (ISC_FTI-BMS) |
| Version | v2.0 |
| Loại | Feature Test Plan |
| Mục tiêu | Xác minh các yêu cầu trong URD được implement đúng (Verify requirements) |
| Framework | Playwright TypeScript |
| Ngày tạo | 2026-06-14 |

---

## 2. Phạm vi (Scope)

### 2.0. Version Context

| Field | Value |
|-------|-------|
| Version | v2.0 |
| Parent version | — (initial version) |
| Delta | Version khởi tạo — toàn bộ features là NEW |
| Input doc | `00_input/v2.0/ISC_FTI-BMS_V2.0_URD_1.0_final.docx` |

### 2.1. Trong phạm vi (In Scope)

| # | Module | Mô tả | Test Approach |
|---|--------|-------|--------------|
| — | Tất cả module trong URD | Xác định sau khi chạy `/analyze-requirements` | Automation |

> ⚠️ Module list sẽ được xác định chính xác sau khi `/analyze-requirements` hoàn thành.

### 2.2. Ngoài phạm vi (Out of Scope)

| # | Module / Feature | Lý do |
|---|-----------------|-------|
| — | Performance testing | Không trong scope v2.0 |
| — | UAT | Không trong scope v2.0 |

---

## 3. Test Approach

| Module | Manual | Automation | Priority | Ghi chú |
|--------|--------|-----------|----------|---------|
| Tất cả module (xác định sau analyze) | ❌ | ✅ Playwright TS | P1 | Scope update sau /analyze-requirements |

**Chiến lược:**
- **Automation-first:** Toàn bộ TC được tự động hoá với Playwright TypeScript
- **Locator strategy:** Ưu tiên `data-testid` → `aria-label` → CSS → XPath
- **Page Object Pattern:** Mỗi page/component = 1 class riêng
- **Source:** `10_source-code/`

---

## 4. Entry & Exit Criteria

### Entry Criteria

| # | Criteria |
|---|---------|
| 1 | Build đã deploy lên STG |
| 2 | Test data đã chuẩn bị xong |
| 3 | Tài liệu requirement đã đặt vào `00_input/v2.0/` ✅ |
| 4 | STG URL đã được cấu hình trong `07_environments/environments.md` |

### Exit Criteria / Quality Gates

| # | Gate | Criteria | Source Skill |
|---|------|----------|-------------|
| G1 | TC Review | Score ≥ 70 | review-tc |
| G2 | P1 Pass Rate | 100% | execute-maintain |
| G3 | Overall Pass Rate | ≥ 90% | execute-maintain |
| G4 | P1 Bugs | 0 open | log-bug |
| G5 | Bug Fix Rate | ≥ 80% | log-bug |
| G6 | Blocked | ≤ 0 | execute-maintain |
| G7 | SRC-TC Match | Score ≥ 70 | review-src-tc |

---

## 5. Test Environment

| Environment | URL | Purpose | Status |
|------------|-----|---------|--------|
| STG | TBD | Primary test environment | ⏳ Chưa có URL |

> ⚠️ STG URL chưa được cấu hình. Cập nhật tại: `07_environments/environments.md`

---

## 6. Resources & Schedule

### Schedule

| Giai đoạn | Bắt đầu | Kết thúc | Owner | Status |
|-----------|---------|----------|-------|--------|
| Test Planning | 2026-06-14 | 2026-06-14 | VanMTT3 | ✅ Done |
| Requirement Analysis | 2026-06-14 | 2026-06-17 | VanMTT3 | ⏳ |
| TC Design & Review | 2026-06-17 | 2026-06-22 | VanMTT3 | ⏳ |
| Automation Implementation | 2026-06-22 | 2026-06-27 | VanMTT3 | ⏳ |
| Execution & Bug Tracking | 2026-06-27 | 2026-06-30 | VanMTT3 | ⏳ |
| Reporting | 2026-06-30 | 2026-06-30 | VanMTT3 | ⏳ |

### Resources

| Thành viên | Vai trò | Module phụ trách |
|-----------|---------|-----------------|
| VanMTT3 | QC Engineer | Tất cả module |

---

## 7. Risk Assessment

| # | Rủi ro | Mức ảnh hưởng | Xác suất | Biện pháp |
|---|--------|-------------|----------|-----------|
| R1 | STG URL chưa sẵn sàng | High | Medium | Theo dõi tiến độ deploy, escalate sớm |
| R2 | Solo resource — QC bị blocked | Medium | Low | Ghi nhận blocker, escalate ngay khi bị block > 1 ngày |
| R3 | URD thay đổi sau khi đã sinh TC | High | Low | Delta re-analysis via `/analyze-requirements --update` |

---

## 8. Deliverables

| # | Deliverable | Folder | Status |
|---|------------|--------|--------|
| 1 | Test Plan | `01_test-plans/TP-Feature-BMS-v2.0.md` | ✅ Done |
| 2 | Requirement Analysis + MASTER-MEMORY | `02_analyze-requirements/v2.0/` | ⏳ |
| 3 | TC-MASTER | `03_test-cases/v2.0/TC-MASTER-v2.0.xlsx` | ⏳ |
| 4 | TC Review Report | `11_tc-review/` | ⏳ |
| 5 | Source Code (Automation) | `10_source-code/` | ⏳ |
| 6 | SRC-TC Review Report | `11_tc-review/` | ⏳ |
| 7 | Test Run Log | `08_test-runs/` | ⏳ |
| 8 | Summary Report | `09_reports/` | ⏳ |

---

## 9. Approval

| Vai trò | Tên | Ngày | Trạng thái |
|---------|-----|------|-----------|
| QC Engineer | VanMTT3 | 2026-06-14 | ✅ |
| QC Lead / PM | — | — | ⏳ |

---

## 10. Revision History

| Version | Date | Changed By | Changes |
|---------|------|-----------|---------|
| 1.0 | 2026-06-14 | VanMTT3 / Claude AI | Initial creation |
