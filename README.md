# MSCS-634-M40-ABDADM
# Walmart Sales Data Analysis Lab

## Purpose of the Lab
The goal of this lab is to practice a complete end-to-end data analysis workflow on a real-world sales dataset. Specifically, we load and preprocess the Walmart sales CSV, explore relationships between key variables using visualizations, perform statistical analyses on weekly sales, and draw insights that could inform business decisions. Along the way, we demonstrate:
- How to inspect and clean data (e.g., handling missing values, detecting outliers).
- How to reduce and transform data for more efficient analysis (sampling, dropping irrelevant columns, scaling, and discretization).
- How to create and interpret visualizations (line plots, histograms, scatter plots, box plots, bar charts, pie charts).
- How to compute and interpret central tendency and dispersion measures, as well as correlation coefficients.

## Key Insights

### Visualizations

1. **Line Plot: Total Weekly Sales Over Time**  
   - The total weekly sales curve (aggregated across all stores) shows two pronounced peaks around the end of 2010 and the end of 2011—both corresponding to year-end holiday seasons. Outside of those spikes, weekly sales remain relatively stable between \$40 million and \$50 million, with occasional smaller bumps (e.g., mid-2011).

2. **Histogram: Distribution of Weekly Sales**  
   - Weekly sales (for individual store-week combinations) are right-skewed: most weeks fall between approximately \$250 k and \$1.5 M, but there is a long tail extending beyond \$2 M. In particular, very few weeks exceed \$2.5 M, indicating that extreme high-sales weeks (often holiday promotions) are rare.

3. **Scatter Plot: Temperature vs. Weekly Sales**  
   - The scatter of temperature against weekly sales is quite dispersed, with virtually no clear linear trend. The computed correlation (≈ −0.038) confirms essentially no meaningful relationship between weekly average temperature and store sales—meaning weather does not appear to drive total revenue at the national level.

4. **Box Plot: Weekly Sales by Holiday Flag**  
   - Non-holiday weeks (Holiday_Flag = 0) have a median around \$975 k and an IQR from roughly \$555 k to \$1.43 M. Holiday weeks (Holiday_Flag = 1) have a slightly higher median (≈ \$1.00 M) and a much wider spread: the top whisker reaches nearly \$3.7 M and there are numerous high outliers. This confirms that holiday weeks not only boost median sales slightly but also generate extreme high-sales outliers.

5. **Bar Chart: Total Weekly Sales by Store (Top 10)**  
   - The top 10 stores (IDs 20, 4, 14, 13, 2, 10, 27, 6, 1, 39) each accumulate over \$220 M in total weekly sales during our sampled period. Store 20 leads with approximately \$300 M. These ten locations together far outpace all other stores, suggesting that resource allocation (e.g., inventory, staffing) should be prioritized there.

6. **Pie Chart: Proportion of Holiday vs. Non-Holiday Weeks**  
   - Only about 7% of store-week records are flagged as holidays (Holiday_Flag = 1), while 93% are non-holiday weeks. Despite being a small fraction of all weeks, holiday weeks account for many of the highest-sales outliers (seen in the box plot), underscoring that holiday events are disproportionately impactful.

### Statistical Measures

1. **Central Tendency for Weekly Sales**  
   - **Min:** \$209,986 (least-active store-week)  
   - **Max:** \$2,678,206 (peak holiday store-week)  
   - **Mean:** \$1,044,816 (average weekly sales per store-week)  
   - **Median:** \$972,478 (50th percentile)  
   - **Mode:** \$209,986 (most frequent single store-week sales, likely a repeated low value)

2. **Dispersion for Weekly Sales**  
   - **Range:** \$2,468,220 (max – min)  
   - **Q1 (25th pct):** \$555,388  
   - **Q3 (75th pct):** \$1,428,969  
   - **IQR (Q3 – Q1):** \$873,581  
   - **Variance:** 2.98 × 10¹¹ (large, reflecting wide spread)  
   - **Standard Deviation:** \$545,653

   The IQR (≈ \$873 k) and large standard deviation (≈ \$546 k) confirm that, although most store-week sales cluster near \$1 M, there is substantial variability—especially due to holiday outliers.

3. **Correlation Analysis**  
   - **Weekly_Sales vs. Temperature_filled:** −0.038 (negligible negative)  
   - **Weekly_Sales vs. Fuel_Price_filled:** +0.033 (very weak positive)  
   - **Weekly_Sales vs. Unemployment:** −0.096 (weak negative)  
   - **Temperature vs. Fuel Price:** +0.140 (weak positive)  
   - **Temperature vs. Unemployment:** +0.095 (weak positive)  
   - **Fuel Price vs. Unemployment:** −0.027 (near zero)

   Overall, none of these factors show a strong linear relationship with weekly sales. The largest magnitude is unemployment at −0.096, but even that is weak. In other words, temperature, fuel price, and unemployment appear to have minimal direct impact on store-level revenue in this dataset.

