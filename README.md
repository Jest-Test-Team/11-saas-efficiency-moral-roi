# SaaS Efficiency, Moral ROI

**中文名稱：** SaaS 功能效率、ROI 與道德影響監測  
**建築學來源：** Operational Energy + POE + Ethical Brief（營運能耗、使用後評估與倫理簡報）

## 核心問題

> 每個 SaaS feature 帶來多少業務價值、資源成本、維運負擔與道德外部性？

## Problem statement

功能成效、infra cost、support burden、security exposure 與 moral impact 分散在不同系統，無法形成 feature-level 決策。

## Inputs

- feature flags
- product analytics
- billing
- support tickets
- security findings
- privacy/accessibility reviews


## Outputs

- Feature Efficiency Card
- ROI/ROE/Externality matrix
- sunset candidates
- portfolio trade-off dashboard


## Primary metrics

| Metric ID | 初始用途 |
|---|---|
| `value_per_compute_unit` | 建立 baseline、趨勢與 review trigger；正式公式見後續 metric registry。 |
| `feature_roi` | 建立 baseline、趨勢與 review trigger；正式公式見後續 metric registry。 |
| `support_burden` | 建立 baseline、趨勢與 review trigger；正式公式見後續 metric registry。 |
| `security_cost` | 建立 baseline、趨勢與 review trigger；正式公式見後續 metric registry。 |
| `moral_externality_index` | 建立 baseline、趨勢與 review trigger；正式公式見後續 metric registry。 |


## MVP scope

1. 建立 feature registry
2. 串接 usage/cost/security
3. 建立 weighted scorecard
4. 輸出 keep/improve/sunset 建議


## Out of scope for MVP

- 自動執行高風險變更
- 以單一分數取代專業審查
- 未經授權蒐集個人、員工、病患或客戶敏感資料
- 宣稱已建立普遍適用的因果關係

## Repository contract

- `project.yaml`：machine-readable project manifest
- `api/openapi.yaml`：最小 ingestion / assessment API
- `schemas/event.schema.json`：事件資料契約
- `docs/architecture.md`：邊界、資料流與 implementation slices
- `docs/threat-model.md`：安全、隱私與濫用風險
- `examples/sample-event.json`：合成資料範例

## First implementation milestone

先完成 **single-tenant, synthetic-data, read-only analysis**。在證據追溯、權限、資料保留與人工覆核尚未建立前，不進入真實組織或個人資料環境。
