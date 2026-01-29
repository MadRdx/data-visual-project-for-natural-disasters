# US Disaster Analytics & Prediction Dashboard

## Project Overview
This project is a comprehensive interactive dashboard designed to visualize, analyze, and predict natural disaster trends across the United States. It integrates historical weather data from NOAA, National Risk Index (NRI) metrics, and machine learning-based projections for 2025 to provide a holistic view of climate-related risks. The platform serves as a powerful tool for researchers, policymakers, and the general public to explore disaster frequency, financial impact, and casualty data through an intuitive geospatial interface.

## Key Features & Functionality
At its core, the application features a dynamic Leaflet-based map that allows users to toggle between historical data (2000-2024) and future predictions (2025). Users can filter by specific disaster types—such as hurricanes, floods, and wildfires—and view detailed state-level statistics. The dashboard is enriched with interactive charts (bar, line, and donut) that break down event frequency, costs, and risk scores. A standout feature is the integrated AI Chatbot, powered by the Groq API, which provides context-aware answers about disaster trends and projections, acting as an intelligent assistant for data interpretation.

## Technical Architecture
The system is built using a robust technology stack combining a Python Flask backend for data serving and API management with a responsive frontend developed in HTML, CSS, and vanilla JavaScript. Data preprocessing pipelines clean and aggregate complex datasets into optimized JSON formats for real-time rendering. The application leverages modern web technologies including Chart.js and Plotly for data visualization, ensuring high performance and a seamless user experience even when handling large datasets.
