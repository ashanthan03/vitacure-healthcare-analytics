# 🏥 VitaCure Healthcare — Operations Analytics Dashboard

**Internship Project | VitaCure Healthcare Private Limited**  
**Analyst:** A. Shanthan Kumar | **Period:** January 2026 – March 2026  
**Tools:** Python · Pandas · Matplotlib · Seaborn · Power BI · DAX

---

## 📌 Project Overview

VitaCure Healthcare is an early-stage home healthcare startup based in Warangal, Telangana, connecting patients with certified physiotherapists for home visits and in-clinic sessions. As a Data Analyst Intern, I was responsible for building an end-to-end analytics solution to help the operations team understand session performance, revenue health, and therapist productivity.

**Business Problem:** The operations team had no structured visibility into session performance, which therapists were driving cancellations, or where the biggest revenue leakage opportunities were.

**Solution Delivered:**
- A clean, analysis-ready dataset with 1,200 session records across 16 features
- A 10-section Python EDA notebook identifying patterns in cancellations, revenue, and patient behaviour
- A 5-page Power BI dashboard for ongoing operational monitoring

---

## 📊 Key Findings

| Finding | Detail |
|---|---|
| Overall Cancellation Rate | High concentration in junior therapists |
| Highest-leakage condition | Post-Stroke Recovery |
| Peak cancellation slot | Monday morning sessions |
| Therapists above avg cancel rate | 2 out of 6 (junior, low experience) |
| Revenue leakage driver | Last-minute cancellations and no-shows |
| Patient retention insight | Majority of patients are returning visitors |

---

## 💡 Recommendations Delivered

1. **Mentorship pairing** for junior therapists with high cancellation rates
2. **Automated reminders** 24hr + 2hr before Monday morning sessions
3. **Late cancellation fee policy** for repeat no-shows
4. **Reassign Post-Stroke cases** to senior therapists (>8 yrs experience)
5. **Expand Teleconsultation** for low-touch conditions to increase volume without facility cost

---

## 📁 Repository Structure

```
vitacure-healthcare-analytics/
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
| Location | Area in Warangal (Warangal / Hanamkonda / Kazipet) |
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
cd vitacure-healthcare-analytics

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
| Cancellation Deep Dive | Day/hour patterns, condition-wise cancel rates, reason breakdown |
| Therapist Performance | Scorecard table, experience vs cancel rate, workload distribution |
| Patient Insights | Retention analysis, visit frequency, location-wise breakdown |

---

## 🔗 Related Project

🤖 **Phase 2 — No-Show Prediction & SQL Analysis (Streamlit App)**  
[https://github.com/ashanthan03/vitacure-noshow-prediction](https://github.com/ashanthan03/vitacure-noshow-prediction)  
Live App: [https://vitacure-noshow-prediction.streamlit.app/](https://vitacure-noshow-prediction.streamlit.app/)

---

*Built as part of a Data Analyst Internship at VitaCure Healthcare Private Limited, Warangal, Telangana.*
