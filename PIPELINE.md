# PIPELINE.md — BMS V2.0 QA Pipeline

> Skill registry + trạng thái từng phase. Cập nhật khi mỗi skill hoàn thành.
> Tester đọc **COMMANDS.md** để biết cách gọi lệnh.

## Skill Registry

| # | Skill | Mô tả | Phase |
|---|-------|--------|-------|
| 1 | `init-project` | Scaffold folder structure + starter files | Setup |
| 2 | `create-test-plan` | Tạo test plan cho version/release | Planning |
| 3 | `analyze-requirements` | Phân tích URD/SRS → scenario map + MASTER-MEMORY | Analysis |
| 4 | `generate-tc` | Sinh test case từ scenarios | TC Design |
| 5 | `editTC` | Chỉnh sửa test case đã sinh | TC Design |
| 6 | `review-tc` | Review TC quality (score ≥ 70) | TC Review |
| 7 | `init-source-code` | Scaffold `10_source-code/` với archetype | Automation |
| 8 | `scan-source-code` | Scan source → populate `10_source-code/MEMORY.md` | Automation |
| 9 | `implement-automation` | Viết Playwright scripts từ TC | Automation |
| 10 | `execute-maintain` | Chạy test + ghi log vào MEMORY §15-§16 | Execution |
| 11 | `log-bug` | Tạo bug report (+ push Jira nếu có) | Bug Tracking |
| 12 | `review-src-tc` | So sánh TC ↔ source code (SRC-TC match) | QA Gate |
| 13 | `test-report` | Sinh báo cáo tổng kết (Excel + HTML dashboard) | Reporting |

## Prerequisites

```
init-project (COMPLETED)
  └─ create-test-plan
       └─ analyze-requirements
            └─ generate-tc → editTC → review-tc
                 └─ init-source-code → scan-source-code → implement-automation
                      └─ execute-maintain ─┬─ log-bug
                                           └─ review-src-tc
                                                └─ test-report
```

## §8 Pipeline Status — v2.0

| Phase | Skill | Status | Ngày hoàn thành | Ghi chú |
|-------|-------|--------|----------------|---------|
| Setup | init-project | ✅ COMPLETED | 2026-06-14 | |
| Planning | create-test-plan | ✅ COMPLETED | 2026-06-14 | TP-Feature-BMS-v2.0.md |
| Analysis | analyze-requirements | ⏳ NOT_STARTED | — | |
| TC Design | generate-tc | ⏳ NOT_STARTED | — | |
| TC Design | editTC | ⏳ NOT_STARTED | — | |
| TC Review | review-tc | ⏳ NOT_STARTED | — | |
| Automation | init-source-code | ⏳ NOT_STARTED | — | Chạy khi cần |
| Automation | scan-source-code | ⏳ NOT_STARTED | — | |
| Automation | implement-automation | ⏳ NOT_STARTED | — | |
| Execution | execute-maintain | ⏳ NOT_STARTED | — | |
| Bug Tracking | log-bug | ⏳ NOT_STARTED | — | |
| QA Gate | review-src-tc | ⏳ NOT_STARTED | — | |
| Reporting | test-report | ⏳ NOT_STARTED | — | |

## Version History

| Version | Status | Ngày | Ghi chú |
|---------|--------|------|---------|
| v2.0 | 🔵 In Progress | 2026-06-14 | Initial version |
