# TWG Power BI / Fabric Control System

Repozytorium projektu architektury danych i dashboardów Power BI dla TWG Polska / NL.

## Cel
Jedno źródło prawdy dla finansów, FTE, forecastu, rentowności klientów, oddziałów i danych operacyjnych.

## Architektura
Sources -> Landing -> Fabric Bronze -> Fabric Silver -> Fabric Gold -> Power BI Semantic Model -> Power BI App -> Alerts / AI

## Zakres MVP
- FactFinancials
- FactInvoices
- FactFTE
- FactForecast
- DimDate
- DimCompany
- DimBranch
- DimClient
- DimAccount
- DimCurrency
- Revenue / Direct Cost / GM / GM%
- Branch Contribution
- Fully Loaded Result
- Actual FTE vs Forecast
- Data freshness / data-quality controls

## Dashboardy
1. Executive
2. Finance
3. Client Profitability
4. Branch Performance
5. Workforce / FTE
6. Cash
7. Data Quality

## Zasady
- Jeden ClientID niezależnie od nazwy źródłowej.
- Missing != 0.
- Brak direct cost = NIEZMAPOWANE.
- Jedna definicja miar w semantic model.
- RLS dla użytkowników biznesowych.
- DEV -> TEST -> PROD.
- AI analizuje certyfikowane miary, nie zastępuje kalkulacji finansowych.

## Bezpieczeństwo
Nie commitować danych osobowych, PESEL, dokumentów legalizacyjnych, danych płacowych pracowników, haseł, connection strings ani kluczy API.

## Referencje
- microsoft/AI-For-Beginners: warstwa edukacyjna AI i Responsible AI
- microsoft/fabric-samples: oficjalne wzorce Microsoft Fabric / Direct Lake / semantic model
