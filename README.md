# Target Facility vs Market Price Benchmarking (2024–2025)

This project contains BigQuery SQL used to benchmark **Target Facility** pricing against the broader market using purchase history data.

The analysis compares Target Facility unit prices to:
- Market averages and medians (2024)
- Market price ranges (min / max) for 2024 and 2025
- Current Target Facility average pricing
- Facility participation thresholds to ensure market stability

---

## 📊 What This Query Produces

For each SKU, the output includes:

### UMC Pricing
- Average, median, min, and max unit price (2024)
- Current average unit price (most recent period)

### Market Benchmarks
- Average and median unit price (2024)
- Minimum and maximum market prices (2024)
- Minimum and maximum market prices (2025)
- Number of facilities contributing to the benchmark
- Number of months with valid market data

### Filters Applied
- Market benchmarks require **at least 5 distinct facilities**
- Rows with missing benchmark or Target Facility pricing data are excluded
- Target Facility is excluded from market calculations

---

## 🧱 Data Sources (Logical)

The query assumes the following logical inputs (names may vary by environment):

- Purchase history with unit price and quantity
- Facility or chain identifiers
- SKU-level identifiers
- Contract or participation metadata (optional)

All logic is written using **standard BigQuery SQL**.

---

## 🧠 Query Structure

The SQL is organized into clear CTEs:

1. **Base purchase data**
2. **Monthly unit price normalization**
3. **Market benchmark calculations (2024)**
4. **Market min/max calculations (2025)**
5. **Target Facility-specific benchmarks**
6. **Final comparison output**

This structure makes the query:
- Easy to debug
- Easy to extend to future years
- Safe to modify without breaking downstream logic

---

## 🚀 How to Use

1. Open `target_facility_market_benchmark.sql`
2. Update dataset or project references as needed
3. Run in BigQuery
4. Export results to:
   - Excel
   - Looker / Looker Studio
   - Tableau
   - Power BI

---

## 🔮 Future Enhancements

Potential next steps:
- Add 2026 market benchmarks
- Flag SKUs where Target Facility is outside market range
- Add volatility or stability indicators
- Visualize market compression over time

---

## 🧾 Notes

- This analysis is designed for **pricing strategy and contracting support**
- Not intended for invoice-level reconciliation
- Benchmarks favor stability over maximum coverage

---

## 👤 Author

**Alyssa Ortega**  
Analytics / Data Science  

