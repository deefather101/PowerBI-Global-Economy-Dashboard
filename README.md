# 🌍 PowerBI Global Economy Dashboard (2010–2025)
Data Analyst | Power BI | SQL | DAX | Transforming Data into Actionable Insights

---

**Objective**:  
This dashboard solves the problem of **tracking macroeconomic health across 100+ countries** by centralizing World Bank data into an interactive tool for:  
- Investors assessing market risks/opportunities  
- Policymakers comparing regional economic performance  
- Analysts identifying correlations between GDP, inflation, and unemployment  

---

## 🛠️ Tools Used  
- **Power BI** (Data modeling, visualization)  
- **Power Query** (Data cleaning & transformation)  
- **DAX** (Key measures: YoY GDP growth, inflation-adjusted trends)  
- **SQL** (Optional: Data extraction if using database sources)  

---

## 🔍 Key Steps  
1. **Data Cleaning**:  
   - Standardized country names (e.g., "Côte d'Ivoire" → "Ivory Coast")  
   - Handled missing values via interpolation for continuous trends  
2. **Transformations**:  
   - Created date hierarchies for time intelligence analysis  
   - Normalized metrics (e.g., GDP in trillions for consistent scaling)  
3. **DAX Logic**:  
   ```dax
   // YoY GDP Growth Measure  
   GDP Growth YoY = 
   VAR CurrentYearGDP = SUM(Data[GDP])  
   VAR PriorYearGDP = CALCULATE(SUM(Data[GDP]), SAMEPERIODLASTYEAR(Data[Date]))  
   RETURN DIVIDE(CurrentYearGDP - PriorYearGDP, PriorYearGDP, 0)  
