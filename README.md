# VoltMart STRIDE Risk Register

This risk register was built using the STRIDE threat modeling framework, applied to the High-sensitivity assets identified in VoltMart's IT asset inventory (`assets.csv`).

## What's in This Repo
- **risk_register.csv** - 12 risk entries covering all 5 High-sensitivity assets, with STRIDE category, likelihood, impact, calculated risk score, owner, and status

## Methodology
For each High-sensitivity asset, I went through the six STRIDE categories (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege) and identified the threats that realistically applied. Each threat was scored on a 1-5 scale for both Likelihood and Impact, and the Risk Score was calculated as Likelihood x Impact. Rows are sorted by Risk Score, highest first.

## Likelihood and Impact Rationale
- **POS Terminals & Database Server (Risk Score 15)**: scored highest because they directly handle payment or business-critical data - a successful attack here has severe, wide-reaching consequences (financial loss, compliance issues).
- **Back Office Laptop (Risk Score 12)**: ransomware is a realistic, fairly common threat for small businesses, and this device holds financial and payroll data, so impact is high even if likelihood is moderate.
- **Backup Drive & Elevation of Privilege risks (Risk Score 10)**: lower likelihood since these require either physical theft or a more targeted attack, but impact remains high due to the sensitivity of exposed data.
- **Remaining risks (Risk Score 8)**: represent realistic but less probable scenarios (e.g., network spoofing, lack of audit logging) with moderate-to-high impact if they occurred.

## Assets Covered
AST-003 (Back Office Laptop), AST-006 (Backup External Hard Drive), AST-010 & AST-011 (POS Terminals), AST-012 (Inventory Database Server)

## Using the Status Column
All risks are currently marked "Open" since mitigations haven't been implemented yet. Going forward, this should be updated to "Mitigated" once a control is in place, or "Accepted" if the business decides a risk is tolerable as-is. Reviewing and updating these statuses should happen alongside the annual risk review.
