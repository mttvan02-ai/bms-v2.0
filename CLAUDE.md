# bms-v2.0 — Project Context

## Thông tin dự án (Project Info)
- **Tên dự án:** BMS V2.0
- **Folder:** `bms-v2.0/`
- **QC phụ trách:** VanMTT3
- **Loại kiểm thử:** Functional
- **Môi trường:** STG
- **URL:** TBD (cập nhật trong `07_environments/environments.md`)
- **Team:** Solo

## Version Info
- **Current version:** v2.0
- **Version history:** v2.0 (initial)
- **MASTER-MEMORY:** `02_analyze-requirements/MASTER-MEMORY.md`
- **Project Rules:** `02_analyze-requirements/Project_rule.md`

## Quy trình làm việc (Workflow)
```
00_input/v2.0/ (tài liệu gốc)
  → 01_test-plans/ (create-test-plan)
    → 02_analyze-requirements/v2.0/ (analyze-requirements)
      → 03_test-cases/v2.0/ (generate-tc → consolidate → TC-MASTER)
        → 11_tc-review/ (review-tc + review-src-tc)
          → 08_test-runs/ (execute)
            → 05_bug-reports/ (log bugs)
              → 09_reports/ (summary report)

Nếu có automation:
  → 10_source-code/ (scan-source → implement-auto → fix-sonar)
  → 11_tc-review/ (review-src-tc: compare TC ↔ code)
  → execute-maintain → log-bug → test-report
```

## MEMORY Files
- **MASTER-MEMORY:** `02_analyze-requirements/MASTER-MEMORY.md` — cross-version registry
- **Version MEMORY:** `02_analyze-requirements/v2.0/MEMORY.md` — version-scoped analysis
- **Source-code MEMORY:** `10_source-code/MEMORY.md` — locators, page classes, implementation log

## Naming Conventions
- Documents: `DOC-v[VERSION]-[NN]`
- Scenarios: `SC-[MODULE]-[NNN]`
- Test cases: `TC-[MODULE]-[NNN]`
- TC Master: `TC-MASTER-v[VERSION].xlsx`
- Bug reports: `BUG-[NNN]-[short-title].md`
- Test runs: `TR-v[VERSION]-[YYYY-MM-DD].md`
- Reports: `REPORT-[TYPE]-v[VERSION]-[DATE].md`

## Folder Reference
| # | Folder | Mục đích | Skill liên quan |
|---|--------|----------|----------------|
| 00 | input/v2.0/ | Tài liệu đầu vào (theo version) | analyze-requirements |
| 00 | input/shared/ | Tài liệu dùng chung | analyze-requirements |
| 01 | test-plans/ | Test plan tổng thể | create-test-plan |
| 02 | analyze-requirements/ | MASTER-MEMORY + Project_rule | analyze-requirements |
| 02 | analyze-requirements/v2.0/ | Analysis output theo version | analyze-requirements |
| 03 | test-cases/v2.0/ | TC-MASTER + fragments | generate-tc |
| 04 | test-data/ | Dữ liệu test | — |
| 05 | bug-reports/ | Báo cáo lỗi | log-bug |
| 06 | checklists/ | Smoke + release checklists | — |
| 07 | environments/ | Config môi trường | — |
| 08 | test-runs/ | Logs chạy test | test-report |
| 09 | reports/ | Báo cáo tổng hợp | test-report |
| 10 | source-code/ | Automation code + MEMORY | scan-source, implement-auto |
| 11 | tc-review/ | Review reports (TC + SRC-TC) | review-tc, review-src-tc |

## Automation
- **Framework:** Playwright TypeScript
- **Source code:** `10_source-code/`
- **MEMORY (source-code):** `10_source-code/MEMORY.md`

## Project Rules
→ Xem chi tiết: `02_analyze-requirements/Project_rule.md`

## Navigation
- **PIPELINE.md** — danh sách 13 skill + trạng thái từng phase
- **COMMANDS.md** — copy-paste lệnh gọi skill, tester đọc file này

## Test Plan — v2.0
- **Document:** `01_test-plans/TP-Feature-BMS-v2.0.md`
- **Type:** Feature Test Plan
- **Scope IN:** Tất cả module trong URD (xác định sau `/analyze-requirements`)
- **Scope OUT:** Performance testing, UAT
- **Approach:** Automation (Playwright TypeScript)
- **Exit criteria (= Quality Gates):** G1-G7 (xem test plan §4)
- **Schedule:** 2026-06-14 → 2026-06-30

## Tools
- Manual testing project scaffolded by `init-manual-project` skill
- Framework version: Multi-Version (MASTER-MEMORY enabled)
- Created on: 2026-06-14
