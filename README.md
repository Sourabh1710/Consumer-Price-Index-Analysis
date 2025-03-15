# Consumer Price Index (CPI) Analysis

Consumer Price Index (CPI) Analysis involves tracking the average price change over time for a basket of goods and services typically consumed by households. It serves as a primary measure of inflation, helping companies and governments understand purchasing power trends, inflationary pressures, and economic stability.
Link to Dataset which ia used in this project. [Dataset](https://statso.io/cpi-analysis-case-study/)

---

## Consumer Price Index Analysis with Python

### Dataset Preprocessing

Before analyzing the data, I noticed that some month values contained extra whitespace, which could cause errors in parsing. Additionally, there was a typo in the `Month` column, such as "Marcrh" instead of "March". To ensure smooth analysis, I cleaned the dataset:

```python
cpi_data['Month'] = cpi_data['Month'].str.strip()
cpi_data['Month'] = cpi_data['Month'].replace('Marcrh', 'March')
cpi_data['Date'] = pd.to_datetime(cpi_data['Year'].astype(str) + '-' + cpi_data['Month'], format='%Y-%B')
```

---

## Inflation Trend Analysis

Now, I analyzed the general CPI index over time for the Rural+Urban sector. This trend helps identify periods of inflationary spikes or stability.

**Trend Analysis Plot:**

![Inflation Trend](https://github.com/Sourabh1710/Consumer-Price-Index-Analysis/blob/main/images/Inflation%20Trend%20Analysis%20(General%20CPI%20Index).png)

From around 2013 to 2023, there is a steady increase in the CPI in India, reflecting a continuous rise in inflation. The general upward trend suggests that the cost of goods and services has gradually increased over this period, with occasional fluctuations. The sharp rise in the last few years indicates a significant inflationary impact, especially around and after 2020.

---

## Seasonal and Cyclical Patterns

To identify patterns, I decomposed the CPI data into seasonal, trend, and residual components.

**Seasonal Decomposition:**

![Seasonal Decomposition](https://github.com/Sourabh1710/Consumer-Price-Index-Analysis/blob/main/images/Seasonal%20Decomposition%20of%20CPI%20(Observed%2C%20Trend%2C%20Seasonal%2C%20Residual).png)

- The **trend line (red)** closely follows the observed CPI values, indicating a steady upward trend over time.
- The **seasonal component (green)** is minimal, suggesting little seasonal fluctuation in the CPI.
- The **residual component (purple)** is close to zero, indicating minimal random variation, implying that the CPI trend is consistent and primarily driven by long-term factors.

---

## Comparison Across Sectors or Regions

I compared the average CPI across different sectors (Rural, Urban, Rural+Urban).

**Sector-Wise CPI Comparison:**

![CPI Comparison](https://github.com/Sourabh1710/Consumer-Price-Index-Analysis/blob/main/images/Average%20CPI%20Comparison%20Across%20Sectors%20(Rural%2C%20Urban%2C%20Rural%2BUrban).png)

The CPI values are relatively consistent across all sectors, with only slight differences, suggesting that inflation affects rural and urban areas similarly. Price changes in goods and services appear to be fairly uniform across these regions.

---

## Correlation with Economic Indicators

To understand interdependencies, I examined the correlation between various categories within the CPI (e.g., Food, Fuel, Health) and the overall General Index.

**Correlation Heatmap:**

![Correlation Heatmap](https://github.com/Sourabh1710/Consumer-Price-Index-Analysis/blob/main/images/Correlation%20between%20CPI%20Categories%20and%20General%20Index.png)

- **High correlations** are observed between Housing, Transport & Communication, and Miscellaneous categories, indicating that changes in these sectors significantly impact the overall CPI.
- **Lower correlations** are seen in categories like Eggs and Vegetables, which suggests more independent or variable price movements in these areas.

---

## CPI and Specific Sector Analysis

I analyzed inflation trends within specific sectors over time.

**Sector-Wise Trend Analysis:**

![Sector Trends](https://github.com/Sourabh1710/Consumer-Price-Index-Analysis/blob/main/images/CPI%20Trends%20for%20Selected%20Sectors.png)

- **Fuel and Light** experienced the steepest increase, particularly after 2020, reflecting higher inflation in this category.
- **Health and Housing** followed a gradual, steady increase over the years, with Health showing a consistent rise.
- **Cereals and Products** exhibited more fluctuations, particularly around 2020, indicating price volatility in this category.

---

## Event-Based Analysis (COVID-19 Periods)

I analyzed CPI trends specifically during the COVID-19 period (2020-2021).

**COVID-19 Impact on CPI:**

![COVID-19 Impact](https://github.com/Sourabh1710/Consumer-Price-Index-Analysis/blob/main/images/CPI%20Trends%20During%20COVID-19%20Period%20(2020-2021).png)

- **Health and Housing** sectors saw notable increases, with Health showing a steady rise and Housing seeing a sharper increase from early 2021.
- **Fuel and Light** experienced a significant decline in early 2020 due to reduced demand during lockdowns, followed by a steep rise in 2021 as economic activities resumed.
- **Cereals and Products** remained relatively stable with minor fluctuations.

Overall, the graph reflects varied inflationary impacts of COVID-19 across different sectors, with essentials like health and housing showing resilience and growth.

---

## Conclusion

### Key Findings:

- **Overall Inflation Trend:** A steady increase in the CPI over the past decade, with inflation particularly rising after 2020.
- **Minimal Seasonal Effect:** The seasonal decomposition shows minimal fluctuations, indicating CPI trends are primarily driven by long-term factors.
- **Rural vs. Urban Impact:** Inflation levels are consistent across rural, urban, and combined sectors, suggesting uniform price changes in these regions.
- **Sectoral Correlations:** Strong correlations between Housing, Transport, and Miscellaneous indicate their significant impact on overall inflation. Categories like Eggs and Vegetables exhibit more independent price movements.
- **Sector-Specific Trends:** Fuel and Light have experienced the steepest price increase, especially post-2020, while Health and Housing show steady inflation growth. Cereals and Products display more volatility.
- **COVID-19 Impact (2020-2021):** Fuel prices initially dropped due to lower demand, then surged in 2021. Health and Housing sectors saw consistent price increases, reflecting inflationary pressures on essential services during this period.

---

## Author
Sourabh Sonker <br>
Data Scientist
