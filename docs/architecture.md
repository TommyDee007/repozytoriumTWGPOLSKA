# Architecture

## Target flow

```
Excel / SharePoint / API / SQL / HR / Accounting / NL
        |
        v
Landing / Ingestion
        |
        v
Fabric Bronze (raw + audit)
        |
        v
Fabric Silver (clean + mapped + validated)
        |
        v
Fabric Gold (business/star model)
        |
        v
Power BI Semantic Model / Direct Lake
        |
        v
Power BI App
        |
        +--> Executive
        +--> Finance
        +--> Client Profitability
        +--> Branch Performance
        +--> Workforce/FTE
        +--> Cash
        +--> Data Quality
```

## Data model

### Facts
- FactFinancials
- FactInvoices
- FactFTE
- FactForecast
- FactRecruitment
- FactWorkerEvents
- FactCashFlow
- FactFX

### Dimensions
- DimDate
- DimCompany
- DimCountry
- DimBranch
- DimClient
- DimProject
- DimService
- DimAccount
- DimCostCategory
- DimOwner
- DimCurrency
- DimSource

## Profitability layers
1. Revenue - Direct Cost = Gross Margin
2. Gross Margin - Branch Controllable Cost = Branch Contribution
3. Branch Contribution - Allocated Central Cost = Fully Loaded Result

## Freshness classes
- Executive finance: 30-60 min
- Operations/FTE: 5-15 min
- API/event sources: 1-5 min where justified

## Data quality gates
- missing != zero
- no 100% margin when direct cost is unmapped
- client and account mappings are mandatory
- common complete period required for cross-branch comparisons
- source load timestamp is visible in every dashboard
