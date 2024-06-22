# Uber Dataset Analysis

This project analyzes Uber ride data across various boroughs of New York City at an hourly level and examines the impact of weather conditions on these rides.

## Data Description

The dataset contains detailed information on Uber rides, including weather conditions at the time of the rides. The attributes in the dataset are:

- `pickup_dt`: Date and time of the pick-up.
- `borough`: NYC's borough.
- `pickups`: Number of pickups for the period (hourly).
- `spd`: Wind speed in miles/hour.
- `vsb`: Visibility in miles to the nearest tenth.
- `temp`: Temperature in Fahrenheit.
- `dewp`: Dew point in Fahrenheit.
- `slp`: Sea level pressure.
- `pcp01`: 1-hour liquid precipitation.
- `pcp06`: 6-hour liquid precipitation.
- `pcp24`: 24-hour liquid precipitation.
- `sd`: Snow depth in inches.
- `hday`: Being a holiday (Y) or not (N).

## Libraries Used

- `pandas` as `pd`
- `numpy` as `np`
- `seaborn` as `sns`
- `matplotlib.pyplot` as `plt`
- `calendar`

## Data Preparation and Cleaning

1. **Reading the Dataset**: Loaded the dataset and displayed the top 5 rows.
2. **Handling Missing Values**: Identified NaN values in `Temperature` and `Holiday` columns.
3. **Invalid Entries**: Detected invalid entries in the `Holiday` column.
4. **Renaming Columns**: Renamed columns for clarity.
5. **Dataset Shape**: The dataset contains 29,101 rows and 13 columns.
6. **Data Types**: 
   - Numeric columns: `PICKUPS`, `WINDSPEED`, `VISIBILITY`, `TEMPERATURE`, `DEW POINT`, `SEA LEVEL PRESSURE`, `PCP01`, `PCP06`, `PCP24`, `SNOW DEPTH`
   - Categorical columns: `BOROUGH`, `HOLIDAY`
7. **Statistical Summary**:
   - Total count of pickup borough and temperature is less than the dataset shape, indicating null values.
   - Wind speed ranges between 0 and 21.
   - Visibility ranges between 0 and 10.
   - Temperature ranges between 0 and 89 (likely an outlier for New York).
8. **Duplicate Values**: Found 0 duplicate entries.
9. **Anomalies**: Identified anomalies in the `Holiday` column.

## Data Cleaning Steps

- Converted `pickup_dt` to datetime format.
- Identified a high correlation between dew point and temperature.
- Removed outliers using the IQR method.
- Imputed missing values:
  - Replaced numeric column null values with the median.
  - Replaced categorical column null values with the mode.

## Key Insights and Analysis

1. **Total Uber Pickups**:
   - Total number of Uber pickups across all boroughs: 3,340,485
2. **Borough with Highest Average Hourly Pickups**:
   - Manhattan has the highest average hourly pickups: 775.30
3. **Pickups by Hour**:
   - Highest number of pickups at 6 AM, lowest at 3 AM.
4. **Pickups by Day of the Week**:
   - Friday has the highest number of pickups (~520,000).
   - Tuesday has the lowest number of pickups (~420,000).
5. **Temperature and Pickups**:
   - Correlation between temperature and pickups: 0.0894
6. **Visibility and Pickups**:
   - Highest pickups when visibility is around 10 miles.
   - Correlation between visibility and pickups: -0.0003
7. **Wind Speed and Pickups**:
   - Correlation between wind speed and pickups: -0.0198
8. **Precipitation and Pickups**:
   - Correlation between PCP01 and pickups: -0.0040
   - Correlation between PCP06 and pickups: -0.0063
   - Correlation between PCP24 and pickups: -0.0162
9. **Holiday and Non-Holiday Pickups**:
   - Pickups on holidays: 131,008
   - Pickups on non-holidays: 3,209,477
10. **Snow Depth and Pickups**:
    - Correlation between snow depth and pickups: -0.0207

## Peak Hours for Uber Pickups in Each Borough

- **Bronx**: 10 PM with 10,650 pickups
- **Brooklyn**: 9 PM with 89,406 pickups
- **EWR**: 7 AM with 331 pickups
- **Manhattan**: 6 AM with 116,196 pickups
- **Queens**: 10 PM with 70,905 pickups
- **Staten Island**: 6 PM with 347 pickups

## Seasonal Analysis

- **Spring**: 1,830,144 pickups
- **Summer**: 628,888 pickups
- **Winter**: 881,453 pickups

## Conclusion

This analysis provides valuable insights into the Uber ride patterns across NYC boroughs, including the impact of weather conditions on ride frequencies. The findings can be used to optimize ride distribution and improve service efficiency.

## Thank You

Thank you for reviewing this project! 😊😊😊

