Climate Change Analysis (Up to 2000)
GitHub
Pytho

This repository contains a detailed analysis of climate change data from various weather stations across India, spanning the years 1901–2000. The dataset includes monthly records of mean maximum and minimum temperatures, as well as rainfall. Using Python, we perform exploratory data analysis (EDA) and visualize trends in temperature and precipitation patterns.

Table of Contents
Overview
Dataset
Installation
Usage
Visualization Examples
Contributing
License
Overview
Climate change has become a critical global issue, and understanding historical climate trends is essential for predicting future scenarios. This project analyzes long-term meteorological data to uncover patterns in temperature and rainfall across different regions in India. By leveraging Python libraries such as pandas, matplotlib, and seaborn, we provide a comprehensive exploration of the dataset through statistical summaries and visualizations.

Dataset
The dataset used in this project is titled climate_change_upto_2000_1.csv. It contains the following columns:

Column Name
Description
Station Name
Name of the weather station
Month
Month of the year
Period
Time period covered by the data (e.g., 1901–2000)
No. of Years
Number of years of recorded data
Mean Temperature in °C - Max
Average maximum temperature
Mean Temperature in °C - Min
Average minimum temperature
Mean Rainfall in mm
Average monthly rainfall

You can find the dataset in the data/ folder of this repository.

Installation
To run the code and reproduce the analysis, follow these steps:

Prerequisites
Python 3.x installed on your system.
Basic knowledge of Python and data analysis libraries.
Steps to Install Dependencies
Clone the repository:

git clone https://github.com/yourusername/climate-change-analysis.git

cd climate-change-analysis

Install the required libraries:

pip install pandas matplotlib seaborn numpy

Run the analysis script:

python analyze_climate_data.py
Usage
Load the Dataset : Use the pandas library to load the CSV file (climate_change_upto_2000_1.csv).
Data Cleaning : Rename columns, handle missing values, and order months chronologically.
Exploratory Data Analysis (EDA) : Perform statistical summaries, group data by station, and identify trends.
Visualization : Generate plots such as line charts, bar plots, heatmaps, boxplots, and scatter plots to explore relationships and trends.
Example Code Snippet:

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Load dataset
df = pd.read_csv("data/climate_change_upto_2000_1.csv")

# Rename columns for easier access
df.columns = ['Station_Name', 'Month', 'Period', 'No_of_Years',
              'Mean_Temp_Max', 'Mean_Temp_Min', 'Mean_Rainfall_mm']

# Define month order
monthly_order = ['January', 'February', 'March', 'April', 'May', 'June',
                 'July', 'August', 'September', 'October', 'November', 'December']
df['Month'] = pd.Categorical(df['Month'], categories=monthly_order, ordered=True)

# Example Visualization: Line Plot of Temperature Trends
station = "Abu"
df_station = df[df["Station_Name"] == station].sort_values("Month")
plt.figure(figsize=(10, 5))
plt.plot(df_station["Month"], df_station["Mean_Temp_Max"], label="Max Temp (°C)", marker="o")
plt.plot(df_station["Month"], df_station["Mean_Temp_Min"], label="Min Temp (°C)", marker="s")
plt.title(f"Monthly Temperature Trends - {station}")
plt.xlabel("Month")
plt.ylabel("Temperature (°C)")
plt.legend()
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
Visualization Examples
Here are some examples of the visualizations generated in this project:

Line Plot : Monthly temperature trends for a specific station.
Bar Plot : Monthly rainfall distribution for a specific station.
Heatmap : Average maximum temperatures across stations and months.
Boxplot : Distribution of maximum temperatures across all stations.
Scatter Plot : Relationship between maximum and minimum temperatures.
Histogram : Distribution of mean rainfall values.
For more details, refer to the notebooks/ or scripts/ folder in this repository.

Contributing
We welcome contributions to this project! If you'd like to contribute, please follow these steps:

Fork the repository.

Create a new branch for your feature or bug fix:
git checkout -b feature-name
Commit your changes:

git commit -m "Add feature or fix"

Push to your branch:

git push origin feature-name
Submit a pull request detailing your changes.
