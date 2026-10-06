# Semantic Model Specification

## Core relationships
- DimDate 1:* Facts
- DimCompany 1:* DimBranch
- DimBranch 1:* Facts
- DimClient 1:* Facts
- DimAccount 1:* FactFinancials
- DimCurrency 1:* FactFinancials / FactInvoices / FactFX

## Mandatory measures
- Revenue
- Direct Cost
- Gross Margin
- Gross Margin %
- Branch Controllable Cost
- Branch Contribution
- Branch Contribution %
- Allocated Central Cost
- Fully Loaded Result
- Fully Loaded Result %
- Actual FTE
- Forecast X
- Forecast Y
- Forecast Attainment %
- Revenue / FTE
- Gross Margin / FTE
- Outstanding AR
- Overdue AR
- Data Freshness
- Unmapped Amount
- Unmapped Records

## Drill path
Group -> Company -> Country -> Branch -> Client -> Project -> Period

## RLS
Business users consume through Viewer/App access.
Roles:
- Board
- Finance
- HR
- Sales
- Branch Manager
- Recruiter
- NL Management
