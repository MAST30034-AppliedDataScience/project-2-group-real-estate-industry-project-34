# Data Documentation

## Introduction
This README provides a brief overview of the datasets used in this project.
  
## Datasets Used

1. **Australian Bureau of Statistics (ABS) Income Data**
   - **Source:**
     - Income data obtained from [Aurin, ABS]([https://www.abs.gov.au/](https://adp-access.aurin.org.au/dataset/au-govt-abs-abs-data-by-region-income-asgs-sa2-2011-2019-sa2-2016))
   - These datasets provide regional income data, including government allowances, which are critical for understanding the financial landscape of different SA2 regions across Australia.

2. **Demographic Data from ABS**
   - **Source:**
     - Demographic data from [ABS](https://www.abs.gov.au/)
   - This dataset provides population and fertility data, which we use to project population growth and future housing demand, especially relevant for student accommodations.

3. **Geospatial Data (Shapefiles)**
   - **Source:**
     - Shapefile from [ABS](https://www.abs.gov.au/statistics/standards/australian-statistical-geography-standard-asgs-edition-3/jul2021-jun2026/access-and-downloads/digital-boundary-files)
   - This shapefile contains geographic boundary data for Statistical Areas Level 2 (SA2). It allows us to map our data spatially and perform location-based analysis.

4. **Crime Data**
   - **Source:**
     - Crime data obtained from [Crime Statistics Agency, Victoria](https://www.crimestatistics.vic.gov.au/)
   - This dataset is used to analyze the impact of crime on rental prices and livability in different regions.

5. **Rental Data**
   - **Source:**
     - Scraped from [domain.com.au](https://www.domain.com.au/)
   - Rental data is collected through web scraping efforts to gather information on current rental prices, property attributes, and availability.


- **Aim**:  
  The objective of this project is to clean and merge income and population data with geographic shapefiles, handle missing values using machine learning techniques, forecast population and income trends, compute affluence scores, and provide insights into future demographic and economic conditions in Victoria.

---

## Datasets: Crime, Income, Fertility (Population), Rental

1. **Years**:  
   - **Income Data**: Data spans 2011 to 2020 for personal income, including various forms of earnings such as employee income, investment income, and government allowances.
   - **Population Data**: Data includes population estimates, fertility rates, and births from 2011 to 2022.
   - **Crime data**: Data includes crime rates per 100000 people per local government area from 2015 - 2024.
   - **Rental Data**: Data includes crime rates per 100000 people per local government area from 2011 - 2024.

2. **Preprocessing**:
   - **Income Data**: Columns with more than 50% missing data were removed. Missing numeric values were imputed using Random Forest Regressor, and rows with null values were dropped.
   - **Population Data**: Missing values were imputed using median values for fertility rates in earlier years. The dataset was cleaned, and columns were renamed to reflect demographic metrics across years.
   - **Geographic Data**: Shapefile data was merged with income and population datasets using the common `Statistical Areas Level 2 2021 code`.
   - **Crime data**: Removed rows irrelevant for analysis per SA2, e.g (Justice Institutions and Immigration Facilities) and converted strings to numerical data
   - **Rental data**: Filtered for rental listings that contain price. Removed outliers (negative price, highly unlikely number of bedrooms and bathrooms, etc.). Missing coordinates were also imputed using google maps API.


3. **Feature Engineering**:
   - **Income Data**: Features related to personal income, investment income, superannuation, and government allowances were used for analysis. After cleaning, the dataset was standardized for PCA.
   - **Population Data**: Features such as population estimates, birth rates, and fertility rates across years were used to forecast future population trends.
   -  **Crime Data**: No feature engineering needed, features were adequate
   - **Rental data**: Date into number of days since January 1, 2011, days on the market, bed and bath interaction, etc, before joining with other metrics: population, distance to public transportation, distance to amenities, etc.

4. **Feature Importance**:
   - **Income Data**: Correlation analysis and Recursive Feature Elimination (RFE) were used to select significant features for income prediction, with PCA applied to reduce dimensionality.
   - **Population Data**: Population and fertility rates were key features used for time series forecasting using the ARIMA model.
   - **Crime Data**: Crime rates throughout the years were all equally important
   - **Rental data**: N/A

5. **Prediction of Future Data (Insights)**:
   - **Income Data**: Linear Regression and PCA were used to predict income trends and compute affluence scores. Forecasts for median income in different suburbs were generated, with affluence scores identifying the most affluent suburbs in Victoria.
   - **Population Data**: ARIMA forecasting predicted population growth for 2023 and 2024, with insights indicating potential future population changes for individual suburbs and the entire state of Victoria.
   - **Crime Data**: Random forest regression was used to predict crime rates for 2011 - 2014 and 2025 - 2027.
   - **Rental data**: N/A




