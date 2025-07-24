# SkySight Analytics: Real-Time Weather & AQI Dashboard in Power BI
A dynamic and interactive Power BI dashboard that visualizes real-time weather conditions and air quality data using WeatherAPI — combining environmental awareness with clean data storytelling.

## Project Overview
The SkySight Analytics Dashboard is designed to provide users with live weather insights and Air Quality Index (AQI) metrics for various cities using data sourced from WeatherAPI.com. This project focuses on creating a powerful, real-time monitoring solution using Power BI Desktop, emphasizing clarity, responsiveness, and user-friendly interactivity.

## Key Features
🌡️ Live Weather Cards: Displays temperature, humidity, wind speed, and other real-time data points using WeatherAPI’s current weather JSON feed.

🧭 Wind Speed Gauges: Visual indicators that show the strength and direction of current wind conditions.

🌍 Map Visualizations: Dynamic map displaying selected cities and their corresponding weather stats.

🔄 City Filters/Slicers: Choose from different cities and instantly update visuals across the report.

💨 Air Quality Index Indicators:

Color-coded AQI levels based on pollutant types like PM2.5, CO, and NO₂.

Status indicators (e.g., Good, Moderate, Hazardous).

Health-based suggestions for users depending on air quality.

🧠 Reusable DAX Patterns: Templates for AQI color, suggestion, and status — easily adaptable for any pollutant.

## Technologies & Tools Used
Power BI Desktop – Data modeling, report building, and interactivity.

WeatherAPI.com – Live weather & AQI data in JSON format.

Power Query Editor – For API integration and data transformation.

DAX (Data Analysis Expressions) – For AQI logic and dynamic indicators.

Custom Visuals & Icons – For enhanced UI/UX.

## How It Works
API Integration:
Fetches live weather and AQI data using a custom URL like:

bash
Copy
Edit
https://api.weatherapi.com/v1/current.json?key=YOUR_API_KEY&q=CITY_NAME
Data Transformation:

Records are expanded in Power Query Editor.

Columns like condition and air_quality are flattened and renamed.

Dashboard Construction:

Cards, Gauges, and Charts visualize weather metrics.

City-based slicers enable location-specific analysis.

Icons and themes are added to enhance readability.

AQI DAX Templates:

AQI Color returns a hex color based on AQI range.

AQI Suggestion outputs a user-friendly message.

AQI Status categorizes the air quality.

## Sample DAX Logic
- DAX
- Copy
- Edit
- AQI Status =
- VAR AQI = ROUND(SELECTEDVALUE('Current'[current.air_quality.pm2_5]), 0)
- RETURN SWITCH(
-    TRUE(),
-    AQI <= 50, "Good",
-    AQI <= 100, "Moderate",
-    AQI <= 150, "Unhealthy for Sensitive",
-    AQI <= 200, "Unhealthy",
-    AQI <= 300, "Very Unhealthy",
-    "Hazardous"
-)


## Learning Outcomes
Real-time API integration within Power BI

Effective use of Power Query for JSON handling

AQI categorization using DAX logic

Enhanced UI/UX through custom visuals and dynamic filters

## Future Enhancements
🔄 Auto-refresh using Power BI Gateway (for live updates)

🌤️ 5-day Forecast Module

📱 Mobile-optimized dashboard layout

🔔 Alert system for severe weather/AQI

## Screenshot of Dashboard :

Show what the dashboard looks like. - ![Alt text](https://github.com/username/repo/assets/image.png)
Example: ![Dashboard Preview](https://github.com/Abhishek-960/Weather-Dashboard/blob/main/Dashboard_Glance.png)
