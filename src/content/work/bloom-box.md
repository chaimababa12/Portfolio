---
title: Dynamic Dashboard
publishDate: 2024-01-01
img: /assets/Projet_Yemen.PNG
img_alt: Overview of the dynamic dashboard for tracking displaced people in Yemen
description: |
  Developed a comprehensive dynamic dashboard to monitor and analyze the displacement of people in Yemen, utilizing data from the Humanitarian Data Exchange platform. This project involved data cleaning, ETL processes using Pentaho, and visualization with Power BI to provide actionable insights on the reasons and trends of population movements.

tags:
  - Data Analysis
  - Power BI
  - Pentaho
  - ETL
  - Data Visualization
---

## Project Overview

### Context and Objectives

The project aimed to understand the reasons behind the displacement of populations in Yemen by analyzing events that caused these movements over time and across different locations. The goal was to provide appropriate visualizations to better comprehend the number of displacements, underlying reasons, and trends of returns or permanent departures.

### Data Sources and Usage

Data was sourced from Excel files obtained from the Humanitarian Data Exchange platform. These files included multiple sheets with information on displacements, returns, and permanent departures for the years 2021 and 2022. Key indicators included the total number of displaced households, affected districts and governorates, and reasons for displacement, whether economic or conflict-related.

### ETL Process and Tools Used

The ETL (Extract, Transform, Load) process was conducted using Pentaho Data Integration (PDI). Key steps included:

- Extracting data from Excel sheets.
- Handling missing values and merging rows.
- Filtering and transforming data to make it usable for dashboard visualization.

### Data Modeling

The project employed a star schema for data modeling, with fact tables including Internal Displaced Persons (IDPs), permanent departures (WhoLeft), and returns (Returnees). Dimensions included governorates, districts, dates, and descriptions of events.

### Visualization

Data visualization was performed using Power BI, creating an interactive and dynamic dashboard that allows stakeholders to track key indicators such as:

- Number of displacements by governorate over various periods (year, month, quarter).
- Reasons for displacement (economic or conflict) in each governorate.
- Patterns of permanent departures and returns.

### Decision-Making Questions

The dashboard addresses several critical questions, including:

- Which governorates and districts are most affected by displacement?
- What are the primary reasons for displacement (economic or conflict) in each governorate?
- How many households are permanently leaving a region, and how many are returning to their place of origin?

### Impact and Utility

This project provides a valuable tool for decision-makers and humanitarian organizations to better understand the dynamics of displacement in Yemen, guiding interventions and resource allocation towards the most critical areas and causes.

The dashboard not only aids in strategic planning but also helps in understanding the humanitarian landscape in Yemen, facilitating timely and informed decision-making for effective crisis response.
