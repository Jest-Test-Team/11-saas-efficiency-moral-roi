# Threat Model — SaaS Efficiency, Moral ROI

## Assets

- evidence data and provenance
- architecture/security/endpoint metadata
- metric definitions and scoring weights
- review decisions and annotations
- tenant boundaries and credentials

## Primary threats

- 將公共價值錯化為短期收入
- 低使用率功能可能服務關鍵少數
- 權重可被管理者操弄

- data poisoning or fabricated evidence
- cross-tenant access
- unauthorized inference about employees, customers or patients
- recommendation tampering
- stale topology or configuration presented as current truth

## Required mitigations

- authenticated ingestion with source identity
- immutable evidence hash and audit trail
- tenant-scoped authorization
- schema and timestamp validation
- rule/model/version pinning
- uncertainty and missing-data display
- human approval for consequential actions
- retention, deletion and correction workflows

## Abuse cases

1. 使用效率或安全分數進行未告知的員工績效監控。
2. 以不完整資料宣稱某團隊、供應商或個人造成事故。
3. 將 research score 當作醫療診斷、保險核保或權利拒絕依據。
4. 以「永續」為名長期保留細粒度裝置與使用行為資料。
