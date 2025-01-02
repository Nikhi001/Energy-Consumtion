# Data Preprocessing Analysis
This repository contains an in-depth analysis of the provided dataset, focusing on data preprocessing techniques and visualization. Below, you'll find details of the steps performed, accompanied by the generated reports and graphs.

## Table of Contents
1. [Introduction](#introduction)
2. [Preprocessing Steps](#preprocessing-steps)
3. [Visualizations](#visualizations)
4. [Reports](#reports)
5. [Conclusion](#conclusion)

## Introduction
This notebook provides insights into the preprocessing pipeline, including handling missing data, feature scaling, encoding, and exploratory data analysis (EDA).

## Preprocessing Steps
# 0.**Problem Statement**

Develop a robust machine learning model to accurately predict appliance energy consumption in households. By utilizing this model, the company aims to improve energy efficiency recommendations, optimize power grid management, and help customers reduce their energy costs.


Attribute Information:
date, time year-month-day hour:minute:second

Appliances, energy use in Wh (target variable for prediction)

lights, energy use of light fixtures in the house in Wh

T1, Temperature in kitchen area, in Celsius

RH_1, Humidity in kitchen area, in %

T2, Temperature in living room area, in Celsius

RH_2, Humidity in living room area, in %

T3, Temperature in laundry room area

RH_3, Humidity in laundry room area, in %

T4, Temperature in office room, in Celsius

RH_4, Humidity in office room, in %

T5, Temperature in bathroom, in Celsius

RH_5, Humidity in bathroom, in %

T6, Temperature outside the building (north side), in Celsius

RH_6, Humidity outside the building (north side), in %

T7, Temperature in ironing room , in Celsius

RH_7, Humidity in ironing room, in %

T8, Temperature in teenager room 2, in Celsius

RH_8, Humidity in teenager room 2, in %

T9, Temperature in parents room, in Celsius

RH_9, Humidity in parents room, in %

To, Temperature outside (from Chievres weather station), in Celsius

Pressure (from Chievres weather station), in mm Hg

RH_out, Humidity outside (from Chievres weather station), in %

Wind speed (from Chievres weather station), in m/s

Visibility (from Chievres weather station), in km

Tdewpoint (from Chievres weather station), Â°C

rv1, Random variable 1, nondimensional

rv2, Random variable 2, nondimensional



**Project Benefits:**

Energy Optimization: The model will help identify factors influencing appliance energy consumption, allowing for more targeted energy-saving strategies.
Cost Reduction: By predicting energy usage accurately, customers can better manage their consumption and reduce energy bills.
Grid Management: Understanding household energy patterns can assist in better power grid management and load balancing.


**Deliverables:**

A documented machine learning model specifically designed for predicting appliance energy consumption.
Comprehensive data visualizations illustrating relationships between various environmental factors and energy usage.
A comparative analysis of different machine learning algorithms for this prediction task.


# 1. **Basic Libraries and Import Data**



# 2. **Perprocessing**

## Report
* RH_6 column is not corrlate with Temperature columns (T1,T2,T3,......T9,T_out)
* RH_Out coloumn is not corrlate with Temperature columns(T1,T2,T3......,T9,T_out)
* Windspeed coloumn is not corrlate with Temperature (T1,T2,T3.......,T9,T_out)
* Tdewpoint columns are corrlate with all Temperature of area and Humidity of areas apart from RH_6 area,press_mm_hg are not corrlate.
* RH_out column is not corrlate with Temperature (T1,....,T9,T_out) however it slightly corrlate with humidity but RH_6 is very corrlate it means"RH_6 area and RH_Out enviroment is same "

## Outlier Analysis

#3. **Feature Engineering And EDA**

---




Extract day,week,month,year,hour from df['date'] column



## Univariate Analysis

### Check Outliers with Boxplot

## **Bivariate Analysis**

### Hourly Energy Consumption Trends

### **weekends and weekdays energy consumptions**


*   Evening Time 18:00 is more energy consumption shown in weekend and weekdays
*   Follow by weekend time between 8 to 11 energy consumption is labber is increased
*   In weekdays used less energy consumption then weekend Or they were not at home





The Magnus-Tetens approximation or the August-Roche-Magnus formula, which is commonly used to estimate dew point or saturation vapor pressure in atmospheric science and meteorology.

This empirical formula is widely referenced in climate science, weather forecasting, and environmental engineering for calculating humidity-related variables.



The formula for dew point is $T_d = \frac{243.04 \times \left( \ln\left(\frac{\text{RH}}{100}\right) + \frac{17.625 \times T}{243.04 + T} \right)}{\left(17.625 - \ln\left(\frac{\text{RH}}{100}\right) - \frac{17.625 \times T}{243.04 + T}\right)}$.

where:
- \( T_d \): Dew point temperature (°C)
- \( T \): Ambient temperature (°C)
- \( \text{RH} \): Relative humidity as a percentage (0-100)


### First Correlation Matrix Observation

- T_out_6 vs. T_out_6: The correlation coefficient is 1.000, indicating a perfect positive correlation with itself, as expected.

- T_out_6 vs. Tdewpoint: The correlation coefficient is 0.662, indicating a strong positive correlation with Tdewpoint.This refers that higher temperatures measured as T_out_6 are associated with higher dew points. but not perfect

- Tdewpoint vs. Tdewpoint: The correlation coefficient is 1.000, indicating a perfect positive correlation with itself.

### Second Correlation Matrix Observation

- Tdew_6 vs. T_dew_6: The correlation coefficient is 1.000, indicating a perfect posistive correlation with itself.

- Tdew_6 vs. Tdewpoint : The correlation coefficient is 1.000, indicating a perfect posistive correlation with itself.

### **Both are calculated in a way that ensures they have identical values.**

## **Multivariate Analysis**

- Appliances can affect both humidity and temperature within a room, sometimes simultaneously increasing one while decreasing the other. For example, air conditioners can lower temperature by dehumidifying the air, while refrigerators and other appliances can release moisture, increasing humidity.

- Relative humidity (RH) is a measure of the amount of water vapor in the air relative to the temperature of the air. The same amount of water vapor will result in higher relative humidity in cooler air than in warmer air.

**Weekdays:**


---



* **Early Morning (0-7 AM)**: Low usage as most people are asleep.  
* **Morning Peak (8 AM - 6 PM)**: Increased usage as people wake up, prepare for work/school, and start their daily routines. This includes activities like cooking, showering, and using electronic devices.  
* **Evening Dip (6 PM - 11 PM)**: Decreased usage as people return home and relax, with some activities like cooking and watching TV.  





**Weekends:**


---


* **Early Morning (0-7 AM)**: Similar to weekdays, low usage during sleep hours.  
* **Morning/Afternoon (8 AM - 4 PM)**: Gradual increase in usage as people wake up later and engage in leisure activities like cleaning, cooking, and using electronic devices.  
* **Afternoon Dip (12 PM - 4 PM)**: A brief period of lower usage, possibly due to outdoor activities or meal times.  
* **Evening Peak (5 PM - 6 PM)**: Another increase in usage as people prepare dinner and engage in evening activities.  
* **Late Evening (6 PM - 11 PM)**: Decreased usage as people wind down for the night.

### **Summary**


*   **Temperature**:- Temperature inside the house varies between 17.76 degrees to 24.779 degrees and outside of the house Temperature between 0.485 degrees to 15.79 degrees
*   **windspeed** :- Windspeed between 2 m\s to 6 m\s they don't have highlighted changes.
*  **Appliances**:- Appliances are drastically changing in the week period.



### **Weekly Energy Utilization with Humidity Inside and Outside**


---



### **Summary**


*   **humidity**:- Inside humidity between 37.05 degrees to 47.85 degrees and outside between 3.28 degrees to 97.56 degrees.
*   **Windspeed**:-wind speed is reamain same over the weeek.



# **Observation**

**1.Diurnal Variation in Indoor Humidity:**

* Indoor humidity fluctuates significantly throughout the day, with peaks during periods of high appliance usage (morning and evening).

* This suggests that appliances, especially those that release moisture (like refrigerators, dishwashers, and clothes dryers), are a major contributor to indoor humidity levels.




**2.Impact of Outdoor Temperature and Humidity on Indoor Conditions:**

* While indoor humidity is primarily influenced by appliance usage, outdoor conditions, especially relative humidity, can also play a role.

* When outdoor humidity is high, it can contribute to higher indoor humidity levels, especially if there is inadequate ventilation.

**3.Stable Outdoor Windspeed:**

* The consistent wind speed throughout the week indicates that wind-driven ventilation is not a significant factor influencing indoor humidity.

**4.Appliance Usage Patterns and Indoor Climate:**

* The correlation between appliance usage patterns and indoor humidity levels highlights the importance of energy-efficient appliances and proper ventilation to maintain optimal indoor air quality.

* By understanding these patterns, homeowners can take steps to reduce energy consumption and improve indoor comfort.

# **Model Training**

## hyperparameters

# **Recommation**

## Recommendations to Client: Optimizing Energy Utilization
Client’s building has higher internal temperatures than ambient air. which suggests the space is artificially heated. Since heating is the primary component of the client’s energy consumption, we have provided a series of recommendations, based on sound architectural and thermodynamic systems design, which aim to:

* reduce consumption
* increase efficiency of existing systems, and
* installation of new systems,
* A detailed cost-analysis can be provided to the client if the scope of work of this contract is extended by consensus.

**A.Retrofitting measures**: One-time, long-term solutions towards power savings

Floor heating, which causes vertical air currents for space heating
Sun-room on the western facing side to capture solar heat
Double-glazed glass walls/windows, which trap heat
Vertical louvers, along south-west walls

**B. Optimization measures:** Reducing energy consumption

- Since weekends during January, February and March see an uptick in consumption levels, it is recommended to switch to solar power during off-peak hours.

- Humidifiers, for frequently occupied shared spaces, would reduce energy consumption
---


*   Multiple ML algorithms were used on the dataset to arrive at the best prediction solution for the client.
*   We have compared the performance of 10 machine learning estimators

  -   Lasso, Ridge, Decision Tree, KNN, Random Forest, Extra Tree Regressor,AdaBoost Regressor,SVR,XGBRegressor,Linear Regression

* ExtraTreeRegressor model provides the best predictions for energy consumption.




# Best R2 score : 66.63%
R2 score on unseen data after hyperparameter tuning, using ExtraTreesRegressor

## Visualizations
![Graph 1](/mnt/data/graph_1.png)

![Graph 2](/mnt/data/graph_2.png)

![Graph 3](/mnt/data/graph_3.png)

![Graph 4](/mnt/data/graph_4.png)

![Graph 5](/mnt/data/graph_5.png)

![Graph 6](/mnt/data/graph_6.png)

![Graph 7](/mnt/data/graph_7.png)

![Graph 8](/mnt/data/graph_8.png)

![Graph 9](/mnt/data/graph_9.png)

![Graph 10](/mnt/data/graph_10.png)

![Graph 11](/mnt/data/graph_11.png)

![Graph 12](/mnt/data/graph_12.png)

![Graph 13](/mnt/data/graph_13.png)

## Reports
Details and summary statistics generated during the analysis can be expanded here.

## Conclusion
The data preprocessing workflow significantly improves the quality and readiness of data for modeling. Further enhancements can be made based on specific project needs.
