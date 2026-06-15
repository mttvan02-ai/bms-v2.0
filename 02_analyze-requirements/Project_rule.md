# Project_rule.md — BMS V2.0

## §1 Project Info
| Field | Value |
|-------|-------|
| Tên dự án | BMS V2.0 |
| Folder | `bms-v2.0/` |
| QC phụ trách | VanMTT3 |
| Loại kiểm thử | Functional |
| Môi trường | STG |
| STG URL | TBD |
| Team mode | Solo |
| Ngôn ngữ TC | Tiếng Việt |
| Automation | Playwright TypeScript |
| TC Version (initial) | v2.0 |
| Ngày tạo | 2026-06-14 |

## §2 Test Types
- [x] Functional
- [ ] Regression
- [ ] Smoke
- [ ] UAT
- [ ] Exploratory
- [ ] Performance

## §3 Environments
| Env | URL | Ghi chú |
|-----|-----|---------|
| STG | TBD | Primary test environment |

## §4 Entry / Exit Criteria
### Entry
- Build đã deploy lên STG
- Test data đã chuẩn bị xong
- Tài liệu requirement đã đặt vào `00_input/v2.0/`

### Exit (Quality Gates)
| Gate | Criteria |
|------|----------|
| G1 | TC Review score ≥ 70 |
| G2 | P1 pass rate = 100% |
| G3 | Overall pass rate ≥ 90% |
| G4 | No P1 bugs open |
| G5 | Bug fix rate ≥ 80% |
| G6 | Blocked ≤ 0 |
| G7 | SRC-TC match score ≥ 70 |

## §5 Naming Conventions
| Artifact | Pattern | Ví dụ |
|----------|---------|-------|
| Document | `DOC-v[VERSION]-[NN]` | DOC-v2.0-01 |
| Scenario | `SC-[MODULE]-[NNN]` | SC-LOGIN-001 |
| Test Case | `TC-[MODULE]-[NNN]` | TC-LOGIN-001 |
| TC Master | `TC-MASTER-v[VERSION].xlsx` | TC-MASTER-v2.0.xlsx |
| Bug Report | `BUG-[NNN]-[short-title].md` | BUG-001-login-fail.md |
| Test Run | `TR-v[VERSION]-[YYYY-MM-DD].md` | TR-v2.0-2026-06-14.md |
| Report | `REPORT-[TYPE]-v[VERSION]-[DATE].md` | REPORT-SUMMARY-v2.0-2026-06-14.md |

## §6 Priority Definition
| Priority | Mô tả |
|----------|-------|
| P1 | Critical — block luồng chính |
| P2 | High — ảnh hưởng nghiêm trọng |
| P3 | Medium — có workaround |
| P4 | Low — cosmetic / minor |

## §7 Severity Definition
| Severity | Mô tả |
|----------|-------|
| Critical | App crash, data loss, security breach |
| High | Core feature không hoạt động |
| Medium | Feature hoạt động nhưng có vấn đề |
| Low | UI/UX, typo, cosmetic |

## §8 Folder Conventions
| Folder | Mục đích |
|--------|----------|
| `00_input/v2.0/` | Tài liệu gốc cho version v2.0 |
| `00_input/shared/` | Tài liệu dùng chung nhiều version |
| `02_analyze-requirements/v2.0/` | Analysis output cho v2.0 |
| `03_test-cases/v2.0/functional/` | TC Functional cho v2.0 |
| `03_test-cases/v2.0/fragments/` | TC fragments chưa merge |

## §9 Automation Rules
- **Framework:** Playwright TypeScript
- **Source:** `10_source-code/`
- **Locator strategy:** Ưu tiên `data-testid` → `aria-label` → CSS → XPath
- **Page Object pattern:** Mỗi page/component = 1 class
- **Skill liên quan:** `init-source-code`, `scan-source-code`, `implement-automation`, `execute-maintain`, `review-src-tc`

## §10 Custom Rules
<!-- Thêm rule riêng của dự án vào đây sau khi kickoff -->

## DOC Notation
req_notation: none
# FR/VR: doc đánh số Functional/Validation Rule (vd kiểu FCP)
# none:  doc không đánh số → traceability dùng DOC-ID §section
# auto:  chưa rõ → analyze-requirements tự phát hiện từ doc ở lần chạy đầu rồi GHI NGƯỢC giá trị thật vào đây
# Detected 2026-06-14: ISC_FTI-BMS_V2.0_URD dùng Description/Actor/Trigger/Pre/Post format, không có số FR/VR/AC/UC.
