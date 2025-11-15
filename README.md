# ROAD ACCIDENT ANALYSIS USING POWER BI
## 📊 Project Overview

This project focuses on analyzing road accident patterns using an interactive Power BI dashboard.
The objective is to help transport authorities and safety teams understand the causes and patterns behind accidents and take data-driven decisions to reduce accident rates.

The dashboard provides deep insights into accident severity, road conditions, weather, vehicle type, time patterns, and location-based trends.

---

## 🗂️ Dataset Description

The dataset contains 21 columns and hundreds of accident records collected from official transportation reports. It includes detailed information such as:

Column Name	Description
Accident_Index	Unique ID for each accident
Accident_Date	Date of the incident
Time	Time of the accident
Day_of_Week	Weekday of occurrence
Accident_Severity	Fatal, Serious, Slight
Vehicle_Type	Type of vehicle involved
Road_Type	Single, Dual, One-way street
Road_Surface_Conditions	Dry, Wet, Frost/Ice
Weather_Conditions	Fine, Rain, Fog, etc.
Light_Conditions	Daylight, Darkness (street lights on/off)
Junction_Detail	T-junction, Crossroads, Roundabout
Urban_or_Rural_Area	Indicates region
Speed_Limit	Legal speed at accident location
Carriageway_Hazards	Roadworks, Slippery roads, etc.

The dataset gives a holistic view of factors contributing to accident severity and frequency.

---

## 📈 Visual Insights
1. Accident Severity Breakdown (Donut / Pie Chart)

Majority of recorded accidents are Slight type.

Serious accidents form a significant portion in urban areas.

Fatal accidents are the least common but highly impactful.

2. Accidents by Day of Week (Bar Chart)

Friday and Saturday have the highest accident counts.

Lowest accidents occur on Monday, indicating reduced traffic flow.

3. Monthly Accident Trend (Line Chart)

Accident frequency peaks during October and December.

Summer months show slightly lower accident counts.

Seasonality patterns indicate high risk during winter months.

4. Weather Condition Impact (Bar Chart)

Most accidents happen in Fine weather, not during rain or fog.
(Indicating that driver behaviour, not weather, is the main cause.)

Rain and snow show lower counts but result in higher severity.

5. Light Condition Analysis (Column Chart)

Majority of accidents occur during daylight hours.

However, night-time accidents under no street lighting have higher severity levels.

6. Vehicle Type Involvement (Tree Map / Bar Chart)

Cars contribute to the highest number of accidents.

Motorcycles show fewer incidents but higher severe cases.

Public transport vehicles show minimal accidents.

7. Urban vs Rural Analysis

Urban areas report significantly more accidents.

Rural accidents are fewer but more likely to be serious or fatal.

8. Speed Limit Effect (Bar Chart)

Speed limit 30 mph zones have the maximum accident count.

Higher speed zones (70 mph) show fewer accidents but higher severity.

---

## 🔧 DAX Measures Used
Total Accidents = COUNT('AccidentData'[Accident_Index])

Serious Accidents = CALCULATE(COUNTROWS('AccidentData'),
                              'AccidentData'[Accident_Severity] = "Serious")

Fatal Accidents = CALCULATE(COUNTROWS('AccidentData'),
                            'AccidentData'[Accident_Severity] = "Fatal")

Monthly Trend = COUNT('AccidentData'[Accident_Index])

Urban Accidents = CALCULATE([Total Accidents],
                            'AccidentData'[Urban_or_Rural_Area] = "Urban")

Rural Accidents = CALCULATE([Total Accidents],
                            'AccidentData'[Urban_or_Rural_Area] = "Rural")

Peak Hour Accidents = 
VAR HourValue = HOUR('AccidentData'[Time])
RETURN IF(HourValue>=17 && HourValue<=20, 1, 0)


## 📈 Dashboard Features

Accident Severity KPIs

Monthly Trend Visualizations

Accidents by Vehicle Type

Weather & Road Condition Impact

Interactive Filters for:

Road Type

Speed Limit

Light Conditions

Vehicle Type

Drillthrough Pages for accident severity analysis

Geographical/Map visualization (when latitude/longitude available)

Heatmaps for peak accident hours

---

## 🧠 Skills Demonstrated

Data cleansing and transformation using Power Query

Building a star schema model for accident reporting

Advanced DAX calculations

Designing intuitive and interactive dashboards

Using slicers, drillthrough, and bookmarks

Turning raw data into actionable road safety insights

Analytical thinking and storytelling with data

---
## 🧰 Tools & Technologies

Power BI Desktop

Excel / CSV data source

DAX (Data Analysis Expressions)

Power Query M Language

---
## 📌 Key Insights from the Road Accident Report
1. 🚧 High Accident Frequency

Urban areas have significantly more accidents than rural regions.

2. 🌤️ Weather Not the Main Cause

Majority of accidents occur during clear weather, not during rain or fog.

3. 🌞 Daylight Has More Accidents

Even though daylight has more accidents, night-time accidents are more severe.

4. 🚗 Cars Are the Major Contributors

Cars form the highest percentage of accidents.

5. 🛵 Motorcycle Accidents Are More Severe

Even though fewer in number, they contribute to higher severity and fatalities.

6. 🕒 Peak Accident Time

5 PM – 8 PM is the most dangerous time window.

7. 🚦 Junctions Are High-Risk Areas

T-junctions and crossroads record the highest incidents.

8. 🔥 Speed Limit of 30 mph Is Most Accident-Prone

High-density traffic zones contribute to more accidents.

9. 🛣️ Road Surface Conditions

Most accidents occur on dry roads, proving that the majority occur due to human error rather than environmental factors.

10. ⚠️ Potential Safety Improvement Areas

Night-time lighting

Traffic control at junctions

Urban mobility management

Awareness programs for bike riders
