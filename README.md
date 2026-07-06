# 🚖 Uber Ride Bookings Analysis — Python EDA

**Tools used:** Python | Pandas | NumPy | Matplotlib | Seaborn | Plotly  
**Status:** Completed

---

## 📌 Short Description

This project performs an end-to-end Exploratory Data Analysis on an NCR (Delhi) Uber ride bookings dataset using Python. I cleaned the raw data, engineered new time-based features, and built 10+ visualizations to understand demand patterns, revenue drivers, vehicle preferences, booking status breakdown, and payment behavior. The goal was to find what is actually driving bookings and revenue — and where the business is losing money through cancellations.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| 🐍 Python | Core language for the entire analysis |
| 🐼 Pandas | Data loading, cleaning, feature engineering, and groupby analysis |
| 🔢 NumPy | Numeric operations and coercion of messy columns |
| 📊 Matplotlib | Static charts — line, bar, and heatmap visuals |
| 🎨 Seaborn | Styled countplots and heatmaps |
| 📈 Plotly | Interactive histogram and scatter plot for ride distance analysis |
| 📓 Jupyter Notebook | Writing and running the full analysis interactively |
| 📁 File Format | `.ipynb` for the notebook, `.csv` for the raw dataset |

---

## 📁 Data Source

**Source:** NCR Ride Bookings Dataset (Kaggle)

The dataset contains individual ride booking records with the following key columns:

- `Booking ID` — Unique identifier per ride
- `Date` / `Time` — When the booking was made
- `Vehicle Type` — Auto, Go Mini, Go Sedan, Prime Sedan, Uber XL, etc.
- `Booking Status` — Completed, Cancelled by Driver, Cancelled by Customer, No Driver Found
- `Booking Value` — Fare amount in ₹
- `Ride Distance` — Trip distance in km
- `Pickup Location` / `Drop Location` — NCR locations
- `Payment Method` — UPI, Cash, Debit Card, Credit Card, Uber Wallet
- `Driver Ratings` / `Customer Rating` — Ratings out of 5

**Features engineered during cleaning:**
- `Hour` — Hour of booking extracted from DateTime
- `DayofWeek` — Day name from DateTime
- `Month` — Month number from DateTime
- `Weekends` — Boolean flag for Saturday and Sunday
- `Is_Successful` — True if booking status is Completed
- `Is_Cancelled_Customer` / `Is_Cancelled_Driver` — Cancellation flags
- `Status Category` — Simplified status: Completed / Cancelled / No Driver Found

---

## 🔍 Features / Highlights

### 🔴 Business Problem

An Uber-style ride booking platform in NCR has thousands of daily bookings — but a large chunk of them never complete. The business needed to understand:

- When is demand highest — and when does it crash?
- Which vehicle types are generating the most revenue?
- Why are 38% of bookings not completing?
- Who is cancelling more — drivers or customers?
- What payment methods do customers prefer?
- Does ride distance actually drive booking value?

---

### 🎯 Goal of the Analysis

To use Python to clean, engineer, and analyze NCR ride booking data — and find patterns in demand, revenue, cancellations, and customer behavior that the raw data alone cannot show.

---

### 📊 Walkthrough of Key Visuals

**Executive KPIs (Printed Metrics)**

| Metric | Value |
|---|---|
| Total Rides Analyzed | 1,50,000 |
| Completed Rides | 93,000 |
| Completion Rate | 62% |
| Total Revenue | ₹4,72,60,574 |
| Average Booking Value | ₹508 |
| Average Ride Distance | 26.0 km |
| Avg Driver Rating | 4.23 / 5 |
| Avg Customer Rating | 4.40 / 5 |
| Customer Cancellations | 10,500 |
| Driver Cancellations | 27,000 |
| Peak Hour | 6 PM |
| Peak Month | July |

---

**Demand Analysis — Bookings by Hour (Line Chart)**

Ride demand follows a clear double-peak pattern —
- Morning peak around 10 AM — office commute hours
- Evening peak at 6 PM — the busiest hour of the entire day
- Lowest demand between 12 AM and 4 AM

---

**Bookings by Day of Week (Bar Chart)**

Demand is fairly consistent across all 7 days — no single weekday dominates. Weekends account for around 40% of all bookings despite being only 2 out of 7 days.

---

**Demand Heatmap — Day vs Hour (Seaborn Heatmap)**

Confirms that 5 PM to 7 PM is consistently the busiest time slot across every day of the week — not just weekdays. The heatmap makes this pattern immediately visible.

---

**Monthly Bookings Trend (Line Chart)**

- July is the peak month for bookings
- February is the lowest month
- No consistent upward or downward trend — demand fluctuates across the year

---

**Revenue by Vehicle Type (Horizontal Bar Chart)**

- Auto is the highest revenue-generating vehicle type at 24.8% of total revenue
- Uber XL contributes only 2% — lowest performing category
- Go Mini and Go Sedan are the next strongest performers

---

**Revenue by Day (Bar Chart)**

Weekends generate approximately 37% of total weekly revenue despite being only 2 days — a clear indicator of where demand concentration sits.

---

**Revenue by Hour (Line Chart)**

- 6 PM is the most profitable hour of the day
- Revenue peaks again around 10 AM
- Consistently low between 12 AM and 4 AM
- Sharp decline after 10 PM

---

**Booking Status Breakdown (Pie Chart)**

| Status | Share |
|---|---|
| Completed | 62% |
| Cancelled by Driver | 18% |
| Cancelled by Customer | 7% |
| No Driver Found | 7% |

38% of bookings are failing — and drivers are the biggest reason why.

---

**Payment Method Distribution (Countplot)**

- UPI dominates at ~45% of all transactions
- Debit Card, Credit Card, and Uber Wallet together make up ~30%
- Cash still accounts for ~24% of transactions

---

**Ride Distance Distribution (Plotly Histogram)**

Shows the spread of trip distances across all bookings — used to understand what the typical ride length looks like in NCR.

---

**Ride Distance vs Booking Value (Plotly Scatter)**

Scatter plot colored by vehicle type to check whether longer rides consistently produce higher fares — and whether vehicle type affects that relationship.

---

### 💡 Business Insights

- **6 PM is the most critical hour** — both bookings and revenue peak here. Driver availability at this time directly impacts revenue.

- **38% of bookings are failing** — this is a major operational problem. Drivers are responsible for 18% of all cancellations — nearly 3x the customer cancellation rate.

- **Weekends punch above their weight** — 2 days generating 37% of weekly revenue means weekend supply needs to match weekend demand.

- **Auto, Go Mini, and Go Sedan carry the business** — these three vehicle types dominate both bookings and revenue. Uber XL is barely contributing.

- **UPI is already dominant at 45%** — cash at 24% is still meaningful but digital is clearly winning.

- **Demand is consistent across weekdays** — no single weekday stands out. The real split is weekdays vs weekends, not Mon vs Fri.

- **July is peak, February is lowest** — operational planning and driver incentives should account for this seasonal swing.

---

### 📌 Recommendations

1. **Fix the driver cancellation problem first** — 18% driver cancellation rate is too high. Incentive structures or penalties need reviewing urgently.

2. **Surge pricing at 6 PM** — peak demand hour with consistent revenue. Pricing optimization here would directly improve margins.

3. **Increase driver supply on weekends** — 40% of bookings and 37% of revenue happen on 2 days. Driver shortages on weekends mean lost revenue.

4. **Invest in Auto, Go Mini, Go Sedan** — these three carry the business. Ensure high driver availability in these categories at all times.

5. **Push UPI incentives further** — already at 45% but reducing cash (24%) further would cut operational cost and improve settlement speed.

6. **Run February promotions** — lowest booking month. A targeted discount or referral campaign could lift demand during this slow period.

7. **Address the No Driver Found problem** — 7% of bookings failing because no driver was available means supply is not meeting demand in certain locations or hours.

---

## 📸 Notebook Preview

*(Add screenshots of your key charts here once uploaded)*

---

## 📂 Project Structure

```
uber-ride-analysis/
├── Uber_ride_analysis.ipynb      ← Full analysis notebook
├── ncr_ride_bookings.csv         ← Raw dataset
└── README.md
```

---

## 💡 What I Learned

- Writing a reusable `clean_data()` function instead of cleaning inline — keeps the notebook organized
- Engineering time features from DateTime — Hour, DayofWeek, Month, Weekends flag
- Using `pd.to_numeric(errors='coerce')` to handle messy numeric columns without breaking the pipeline
- Choosing between Matplotlib, Seaborn, and Plotly depending on what the chart needs
- Using Plotly for interactive scatter and histogram when static charts are not enough
- Thinking about cancellation rates as a business metric, not just a data cleaning step

---

## 🙋 Connect with Me

This is part of my ongoing data analytics learning journey. If you have feedback on the analysis, the code structure, or the charts — I would genuinely like to hear it.

- 🔗 LinkedIn: [linkedin.com/in/tarun-kumar-5b9280396](https://linkedin.com/in/tarun-kumar-5b9280396)
- 💻 GitHub: [github.com/tarunkumar7906](https://github.com/tarunkumar7906)

---

*Still learning. Open to feedback.*
