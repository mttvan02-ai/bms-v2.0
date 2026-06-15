# MASTER-MEMORY — Cross-Version Registry

> Cập nhật lần cuối: 2026-06-14
> Active version: v2.0

## 1. Version Registry

| Version | Release Date | Input Folder | Analyze Folder | Status | Tổng DOC | Tổng SC (all) | Tổng SC (new+mod) | Parent |
|---------|-------------|-------------|----------------|--------|----------|--------------|-------------------|--------|
| v2.0 | 2026-06-14 | 00_input/v2.0/ | 02_analyze-requirements/v2.0/ | In Progress | 1 | 40 | 40 | — (initial) |

## 2. DOC ID Registry (Global)

| DOC ID | Version | File | Loại | Modules |
|--------|---------|------|------|---------|
| DOC-v2.0-01 | v2.0 | ISC_FTI-BMS_V2.0_URD_1.0_final.docx | URD | DASH, CH, PDC, BC, CD, KH |

## 3. Scenario Lifecycle (Cross-Version)

> Version đầu tiên — tất cả SC = NEW. Roll-up per module.

| Module | Origin | Lifecycle | Count |
|--------|--------|-----------|-------|
| DASH (Dashboard) | v2.0 | NEW | 6 |
| CH (Cơ hội) | v2.0 | NEW | 15 |
| PDC (Phê duyệt cơ hội) | v2.0 | NEW | 5 |
| BC (Báo cáo) | v2.0 | NEW | 4 |
| CD (Cài đặt & Cấu hình) | v2.0 | NEW | 4 |
| KH (Khách hàng / Lead / CV / DH) | v2.0 | NEW | 6 |

## 4. Regression Scope

### v2.0
**Phải test (new + modified):**

| SC ID | Type | Lý do |
|-------|------|-------|
| SC-DASH-001 đến SC-DASH-006 | NEW | Version đầu — toàn bộ cần test |
| SC-CH-001 đến SC-CH-015 | NEW | Version đầu — toàn bộ cần test |
| SC-PDC-001 đến SC-PDC-005 | NEW | Version đầu — toàn bộ cần test |
| SC-BC-001 đến SC-BC-004 | NEW | Version đầu — toàn bộ cần test |
| SC-CD-001 đến SC-CD-004 | NEW | Version đầu — toàn bộ cần test |
| SC-KH-001 đến SC-KH-006 | NEW | Version đầu — toàn bộ cần test |

**Nên regression (carried — high risk):** N/A — version đầu tiên.

**Không cần test (carried — low risk, stable):** N/A — version đầu tiên.

## 5. Version Comparison

N/A — v2.0 là version đầu tiên.

## 6. TC Files Registry

| Version | TC-MASTER File | Tổng TC | Ngày consolidate | Status |
|---------|---------------|---------|-------------------|--------|
| v2.0 | 03_test-cases/v2.0/TC-MASTER-v2.0.xlsx | — | — | NOT_STARTED |

## 7. Downstream Path Registry

| Skill | Active Version Path |
|-------|-------------------|
| generate-tc | 02_analyze-requirements/v2.0/MEMORY.md |
| review-tc | 03_test-cases/v2.0/TC-MASTER-v2.0.xlsx |
| implement-automation | 10_source-code/ |
| vibe-test | 03_test-cases/v2.0/ |
| test-report | 09_reports/ |

## 8. Pipeline Status — v2.0

> Thứ tự + tên skill khớp PIPELINE.md. Status ∈ NOT_STARTED / IN_PROGRESS / PARTIAL / COMPLETED / SKIPPED / FAILED.

| # | Skill | Status | Last Run | Scope | Output | Notes |
|---|-------|--------|----------|-------|--------|-------|
| 0.5 | init-source-code | NOT_STARTED | — | — | — | optional, playwright-ts |
| 1 | init-project | COMPLETED | 2026-06-14 | — | CLAUDE.md/PIPELINE.md/COMMANDS.md | — |
| 2 | create-test-plan | COMPLETED | 2026-06-14 | v2.0 | TP-Feature-BMS-v2.0.md | Feature test plan |
| 3 | analyze-requirements | COMPLETED | 2026-06-14 | v2.0 (INIT) | MASTER-MEMORY + 5 files v2.0 | DOC-v2.0-01, 40 SC, 8 CL |
| 4 | generate-tc | NOT_STARTED | — | — | — | — |
| 5 | review-tc | NOT_STARTED | — | — | — | — |
| 6 | scan-source-code | NOT_STARTED | — | — | — | — |
| 7 | implement-automation | NOT_STARTED | — | — | — | — |
| 8 | review-src-tc | NOT_STARTED | — | — | — | — |
| 9 | vibe-test | NOT_STARTED | — | — | — | — |
| 10 | execute-maintain | NOT_STARTED | — | — | — | — |
| 11 | log-bug | NOT_STARTED | — | — | — | — |
| 12 | test-report | NOT_STARTED | — | — | — | — |
| 13 | health-check | COMPLETED | 2026-06-14 | QUICK | inline chat | 0 CRITICAL, 0 WARNING, 4 INFO (early-stage expected) |

## 9. Notes

- 2026-06-14: INIT analysis cho v2.0. URD chỉ có đặc tả chi tiết cho 2/27 chức năng (DASHBOARD + TẠO CƠ HỘI). 22 chức năng còn lại chỉ có mô tả ngắn trong danh sách chức năng → scenario ở mức high-level, cần spec bổ sung.
- Ma trận phân quyền: "theo link" (external link trong URD, không accessible) → C-GEN-001 BLOCKER.
- `req_notation: none` — URD không đánh số FR/VR/AC/UC.
