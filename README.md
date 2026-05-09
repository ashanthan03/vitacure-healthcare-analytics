# 🏥 VitaCure Healthcare — Operations Analytics Dashboard

**Internship Project | VitaCure Healthcare Private Limited**  
**Analyst:** A. Shanthan Kumar | **Period:** July 2024 – September 2024  
**Tools:** Python · Pandas · Matplotlib · Seaborn · Power BI · DAX

---

## 📌 Project Overview

VitaCure Healthcare is an early-stage physiotherapy startup operating across 5 Indian cities. As a Data Analyst Intern, I was responsible for building an end-to-end analytics solution to help the operations team understand session performance, revenue health, and therapist productivity.

**Business Problem:** The operations team had no structured visibility into why revenue was underperforming month-on-month, which therapists were driving cancellations, or where the biggest leakage opportunities were.

**Solution Delivered:**
- A clean, analysis-ready dataset with 1,200 session records across 16 features
- A 10-section Python EDA notebook identifying root causes of ₹4.14L in revenue leakage
- A 5-page Power BI dashboard for ongoing operational monitoring

---

## 📊 Key Findings

| Finding | Metric |
|---|---|
| Overall Cancellation Rate | 21.8% |
| Total Revenue Leakage (6 months) | ₹4,14,067 |
| Leakage as % of Potential Revenue | ~22% |
| Therapists above avg cancel rate | 2 (Rohan Verma: 41.3%, Arjun Nair: 35.0%) |
| Highest-leakage condition | Post-Stroke Recovery |
| Peak cancellation slot | Monday 9–11 AM |

---

## 💡 Recommendations Delivered

1. **Mentorship pairing** for junior therapists with high cancellation rates → estimated 15% reduction
2. **Automated reminders** 24hr + 2hr before Monday morning sessions → estimated 20% reduction in Monday cancellations
3. **Late cancellation fee** of ₹200 for no-shows → estimated ₹40K/month leakage recovery
4. **Reassign Post-Stroke cases** to senior therapists (>8 yrs experience)
5. **Expand Teleconsultation** for low-touch conditions to increase volume without facility cost

---

## 📁 Repository Structure

```
vitacure-analytics/
│
├── vitacure_dataset.csv              # Cleaned dataset (1,200 rows × 16 features)
├── VitaCure_EDA_Analysis.ipynb       # Full Python EDA notebook (executed)
├── vitacure_dashboard.pbix           # Power BI Dashboard (5 pages)
├── dax_measures.md                   # All DAX measures used in Power BI
└── README.md
```

---

## 🗂️ Dataset Description

| Column | Description |
|---|---|
| Session_ID | Unique session identifier |
| Patient_ID | Unique patient identifier (for retention tracking) |
| Date | Session date |
| Day_of_Week | Day name (for pattern analysis) |
| Hour | Scheduled hour (9–19) |
| Therapist | Treating physiotherapist name |
| Therapist_Experience_Years | Years of experience |
| Condition | Medical condition being treated |
| Session_Type | In-Clinic / Home Visit / Teleconsultation |
| City | Patient city |
| Payment_Mode | UPI / Cash / Insurance / Card |
| Session_Duration_mins | Duration in minutes (0 if cancelled) |
| Cancelled | 1 = Cancelled, 0 = Completed |
| Cancellation_Reason | Reason (if cancelled) |
| Realized_Revenue | Revenue collected (₹) |
| Revenue_Leakage | Revenue lost to cancellation (₹) |

---

## 🛠️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/ashanthan03/vitacure-healthcare-analytics.git
cd vitacure-analytics

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch the notebook
jupyter notebook VitaCure_EDA_Analysis.ipynb
```

---

## 📈 Power BI Dashboard Pages

| Page | Focus |
|---|---|
| Executive Overview | High-level KPIs, revenue summary, cancellation rate |
| Revenue Analytics | Monthly trends, condition-wise revenue, payment mode split |
| Cancellation Deep Dive | Day/hour heatmap, condition-wise cancel rates, reason breakdown |
| Therapist Performance | Scorecard table, bubble chart, workload distribution |
| Patient Insights | New vs returning, visit frequency, city-wise analysis |

---

*Built as part of a Data Analyst Internship at VitaCure Healthcare Private Limited.*
