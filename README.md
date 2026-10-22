# Tracking the Ripple Effect: The Relationship Between Irish Fuel Prices and Grocery Inflation (2016–2026)

## 📌 Project Overview

Inflation has been one of the most pressing economic challenges for Irish households in recent years. While public discourse frequently links spikes in supermarket grocery prices directly to rising fuel and energy costs, the precise relationship, magnitude, and timeline of this transmission remain complex.

This project investigates how fluctuations in retail fuel prices (Petrol and Diesel) correlate with food and non-alcoholic beverage prices in Ireland over a robust 10-year timeline (2016–2026). By extending the analysis through 2026, the project captures extreme recent macroeconomic shocks—including the maritime trade and energy disruptions at the Strait of Hormuz—providing a unique lens on how severe geopolitical choke-points immediately impact Irish transport fuel and subsequently ripple into household grocery inflation.

## 👥 Team Members

Ahlam Khalil

Sara Larkem

Chenrui Xie

## 📊 Dataset Source and Description

Source: Central Statistics Office (CSO) Ireland, Consumer Price Index (Table CPM24 - Detailed Sub Indices).

Time Span: January 2016 to September 2026 (129 continuous monthly observations with zero missing values).

Key Variables Tracked:

Petrol Index

Diesel Index

Food and Non-Alcoholic Beverages Index

## 🎯 Core Research Questions

Correlation & Co-movement: What is the statistical strength of the relationship between fuel price movements and grocery price changes in Ireland?

Time-Lag Dynamics: Do grocery prices respond immediately to fuel price spikes, or is there a delayed transmission (time-lag) through the supply chain? (Preliminary exploration indicates a stronger correlation when applying a multi-month lag).

Impact of Significant World Events & Geopolitical Shocks: How did major macroeconomic turning points—specifically the COVID-19 pandemic (2020), the Ukraine war energy crisis (2022), and recent maritime disruptions at the Strait of Hormuz—disrupt or amplify price volatility and the gap between fuel and food inflation?

## 🛠️ Methodology & Tech Stack

Data Processing & Cleaning: Python (pandas, numpy) executed within Google Colab to reshape, clean, and format the raw CSO dataset.

Exploratory Data Analysis (EDA): Statistical calculations including correlations, time-lag analysis, and month-over-month percentage changes (inflation volatility).

Data Visualization & Event Overlay: matplotlib and seaborn to produce multi-variable time-series charts annotated with vertical milestone lines for major historical world events and geopolitical supply shocks.

## 📂 Repository Structure

/data - Raw and cleaned datasets from the CSO.

/notebooks - Jupyter/Colab notebooks containing data processing, EDA, and visualization code.

/assets - Exported charts, graphics, and visualizations used for the final report.

## 🚀 Expected Deliverables

A clean, reproducible Jupyter/Colab notebook.

Professional multi-variable time-series visualizations incorporating historical shock annotations.

A comprehensive final report detailing findings on supply chain cost transmissions in the Irish retail market.
