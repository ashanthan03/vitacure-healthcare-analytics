# VitaCure Power BI — DAX Measures
## Copy-paste these into Power BI Desktop → New Measure

---

## KPI Cards

```dax
-- Total Sessions
Total Sessions = COUNTROWS(vitacure_dataset)

-- Total Realized Revenue
Total Revenue = SUM(vitacure_dataset[Realized_Revenue])

-- Total Revenue Leakage
Total Leakage = SUM(vitacure_dataset[Revenue_Leakage])

-- Cancellation Rate %
Cancellation Rate % = 
    DIVIDE(
        COUNTROWS(FILTER(vitacure_dataset, vitacure_dataset[Cancelled] = 1)),
        COUNTROWS(vitacure_dataset)
    ) * 100

-- Leakage % of Potential
Leakage % = 
    DIVIDE(
        [Total Leakage],
        [Total Revenue] + [Total Leakage]
    ) * 100

-- Average Session Value (completed only)
Avg Session Value = 
    CALCULATE(
        AVERAGE(vitacure_dataset[Realized_Revenue]),
        vitacure_dataset[Cancelled] = 0
    )

-- Unique Patients
Unique Patients = DISTINCTCOUNT(vitacure_dataset[Patient_ID])

-- Returning Patients
Returning Patients = 
    COUNTROWS(
        FILTER(
            SUMMARIZE(vitacure_dataset, vitacure_dataset[Patient_ID], "Visits", COUNTROWS(vitacure_dataset)),
            [Visits] > 1
        )
    )

-- Retention Rate %
Retention Rate % = 
    DIVIDE([Returning Patients], [Unique Patients]) * 100
```

---

## Revenue Analytics

```dax
-- Month-over-Month Revenue Growth %
MoM Revenue Growth % = 
    VAR CurrentMonth = [Total Revenue]
    VAR PreviousMonth = CALCULATE([Total Revenue], DATEADD(vitacure_dataset[Date], -1, MONTH))
    RETURN
        IF(
            ISBLANK(PreviousMonth),
            BLANK(),
            DIVIDE(CurrentMonth - PreviousMonth, PreviousMonth) * 100
        )

-- Revenue Target (set to 10% above previous month — adjust as needed)
Revenue Target = 
    CALCULATE([Total Revenue], DATEADD(vitacure_dataset[Date], -1, MONTH)) * 1.10
```

---

## Therapist Performance

```dax
-- Therapist Cancellation Rate %
Therapist Cancel Rate % = 
    DIVIDE(
        CALCULATE(COUNTROWS(vitacure_dataset), vitacure_dataset[Cancelled] = 1),
        COUNTROWS(vitacure_dataset)
    ) * 100

-- Therapist Revenue per Session
Revenue per Session = 
    DIVIDE(
        CALCULATE(SUM(vitacure_dataset[Realized_Revenue]), vitacure_dataset[Cancelled] = 0),
        CALCULATE(COUNTROWS(vitacure_dataset), vitacure_dataset[Cancelled] = 0)
    )

-- Flag: High Cancellation Therapist (>25%)
High Cancel Flag = 
    IF([Therapist Cancel Rate %] > 25, "⚠️ High Risk", "✅ Normal")
```

---

## Conditional Formatting Color Measures

```dax
-- KPI Color — Cancellation Rate (red if > 25%)
Cancel Rate Color = 
    IF([Cancellation Rate %] > 25, "#E05A2B", "#1A6B8A")

-- KPI Color — Leakage % (red if > 20%)
Leakage Color = 
    IF([Leakage %] > 20, "#E05A2B", "#1A6B8A")
```

---

## Usage Notes
- All measures assume the table is named `vitacure_dataset` — rename if yours differs
- For time-intelligence measures (MoM Growth), ensure your Date column is marked as a Date Table in Power BI
- The `Flag` measures can be used in a table visual's conditional formatting field
