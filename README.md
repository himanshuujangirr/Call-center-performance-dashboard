
# Call Center Performance Dashboard – Power BI

This repository presents an end-to-end business intelligence solution developed using Power BI. The project focuses on analyzing call center performance data through interactive dashboards and key metrics. It is specifically designed for customer service managers, business analysts, and operational teams to gain insights into performance drivers, service level adherence, and customer sentiment trends.

## Objective

The goal of this project is to build a comprehensive dashboard that provides:
- Real-time visibility into key operational metrics
- Performance benchmarking across states, cities, and channels
- Insight into customer sentiment and reasons for contact
- Tools to enhance decision-making and resource allocation

## Tools and Technologies Used

- Power BI Desktop: Primary tool for building and visualizing the dashboard
- Power BI Service: Used for publishing and sharing dashboards
- DAX (Data Analysis Expressions): For writing custom KPIs and calculated measures
- CSV File: Source data used for building the dashboard
- UTM with Windows 11 ARM (Power BI on Mac M1): Virtual machine setup for Power BI compatibility on macOS

## Dataset Overview

The dataset contains 32,941 rows of call center records, with the following key fields:
- Id: Unique call identifier
- Call Timestamp: Date of call
- Call-Centres City: Location of the call center
- Channel: Communication mode (Call-Center, Chatbot, Email, Web)
- City and State: Customer's location
- Reason: Reason for the call (e.g., Billing, Payments, Service Outage)
- Response Time: SLA status (Within SLA, Above SLA, Below SLA)
- Sentiment: Inferred customer sentiment from the interaction
- Call Duration In Minutes: Duration of the call
- Csat Score: Customer satisfaction score (0–10 scale)

## Features and Functionalities

### KPI Cards
- Total Calls: Total number of customer interactions
- Total Duration (Hours): Total duration of all calls in hours
- Average Call Duration: Mean duration per call
- Response Time %: Percentage of calls handled within SLA

### Visualizations
- Calls by Day Name: Identifies busiest days for calls
- Calls by State: Highlights regions with highest call volume
- Calls by Reason: Displays top reasons for customer contact
- Calls by Channel: Evaluates performance of different communication modes
- Sentiment by Channel: Analyzes customer sentiment distribution per channel
- Calls by Call Center City: Examines performance of call center locations

### Tabular Grid
- Full record breakdown with conditional formatting
- Filter and export functionality for detailed analysis

### Filters and Slicers
- Date Range: Select custom time periods
- Channel Filter: Analyze by communication mode
- Response Time Filter: Slice data based on SLA performance

## Key DAX Measures

```
Total Calls = COUNT(CallData[Call ID])

Total Duration (Hours) = SUM(CallData[Call Duration In Minutes]) / 60

Average Call Duration = AVERAGE(CallData[Call Duration In Minutes])

Response Time % = 
DIVIDE(
    CALCULATE(COUNTROWS(CallData), CallData[Response Time] = "Within SLA"),
    COUNTROWS(CallData),
    0
)
```

## Project Highlights

- Focused on operational performance and service efficiency
- Combines quantitative metrics with qualitative sentiment analysis
- Uses intuitive, interactive visual elements to enhance understanding
- Enables data-driven decisions in customer service environments

## Usage

This dashboard can be used by:
- Business Analysts to track KPIs and recommend improvements
- Customer Service Managers to evaluate agent performance and SLA compliance
- Operations Teams to identify bottlenecks and peak hours

## How to Run the Project

1. Clone this repository or download the `.pbix` file (if included)
2. Open the file in Power BI Desktop
3. Load the dataset if prompted or update path to the CSV file in the Power Query editor
4. Explore the dashboard and interact with slicers and filters

## License

This project is released under the MIT License. You are free to use, distribute, and modify it with attribution.

