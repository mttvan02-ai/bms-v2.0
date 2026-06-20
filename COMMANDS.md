# COMMANDS.md — BMS V2.0

> Copy-paste lệnh gọi skill. Xem PIPELINE.md để biết trạng thái từng phase.

---

## Phase 1 — Planning

### Tạo Test Plan
```
/create-test-plan --create
```

---

## Phase 2 — Analysis

### Phân tích tài liệu requirement (lần đầu)
```
/analyze-requirements --init @00_input/v2.0/
```

### Phân tích version mới (delta)
```
/analyze-requirements --delta v2.1 @00_input/v2.1/
```

### Rà soát completeness (sweep)
```
/analyze-requirements --sweep
```

---

## Phase 3 — TC Design

### Sinh test case từ scenarios
```
/generate-tc
```

### Chỉnh sửa test case
```
/editTC
```

---

## Phase 4 — TC Review

### Review chất lượng TC
```
/review-tc
```

---

## Phase 5 — Automation

### Scaffold source code (lần đầu)
```
/init-source-code --archetype playwright-ts
```
> Archetypes có sẵn: `playwright-ts` (web), `selenium-java` (web), `appium-java` (mobile)

### Scan source code
```
/scan-source-code
```

### Implement automation scripts
```
/implement-automation
```

---

## Phase 6 — Execution

### Chạy test
```
/execute-maintain
```

### Chạy test với scope cụ thể
```
/execute-maintain --scope smoke
/execute-maintain --scope regression
```

---

## Phase 7 — Bug Tracking

### Log bug mới
```
/log-bug
```

---

## Phase 8 — QA Gate

### So sánh TC ↔ Source Code
```
/review-src-tc
```

---

## Phase 9 — Reporting

### Sinh báo cáo tổng kết
```
/test-report
```

---

## Utility Commands

### Health check workspace
```
/health-check
```

### Phân tích yêu cầu (alias)
```
/analyze
```

---

## Pipeline Flow (Automation = YES)

```
/create-test-plan
  → /analyze-requirements --init @00_input/v2.0/
    → /generate-tc → /editTC → /review-tc
      → /init-source-code --archetype playwright-ts
        → /scan-source-code
          → /implement-automation
            → /execute-maintain
              → /log-bug (nếu có bug)
              → /review-src-tc
                → /test-report
```
