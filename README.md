TerSpegelt Review Analysis & Dashboard
This repository contains an automated data pipeline and a Streamlit dashboard designed to analyze guest reviews for TerSpegelt. The project integrates sentiment analysis and topic modeling with historical weather and holiday data (2017–present) to provide management with actionable insights.
Key Features
Automated Pipeline: Processes raw review data through cleaning, sentiment analysis, topic modeling, and enrichment with external datasets.

Sentiment & Topic Modeling: Breaks down reviews into specific topics and labels them as Positive, Neutral, or Negative.

External Data Integration: Correlates guest satisfaction with max temperatures, precipitation levels, and holiday periods (2017–2025).

Interactive Dashboard: A Streamlit-based interface featuring:

High-level metrics (Satisfaction scores, negative feedback counts).

Visualizations of sentiment per topic.

Weather impact analysis (Rain and Temperature vs. Satisfaction).

Deep-dive tools including Word Clouds for negative feedback and filterable review tables.

Installation
Clone the repository:

Bash

git clone https://github.com/ScottLaans/mini_project.git
cd mini_project
Install dependencies: Ensure you have Python installed, then run:

Bash

pip install -r requirements.txt
Required packages include streamlit, pandas, plotly, statsmodels, wordcloud, and matplotlib.

Usage
1. Run the Data Pipeline
Before launching the dashboard, you must run the automated pipeline to process the raw data and generate the final dataset (final_data_for_powerbi.json).

Bash

python run_pipeline.py
The pipeline executes the following scripts in order:

clean_reviews.py: Cleans and prepares the raw review text.

analyse_sentiment.py: Assigns sentiment labels and scores.

analyse_topics.py: Identifies key themes within the reviews.

merge_with_weather.py: Integrates historical weather data.

add_holidays.py: Labels reviews based on Dutch holiday periods.

Note: The pipeline automatically removes intermediate JSON files after completion to keep the workspace clean.

2. Launch the Dashboard
Once the pipeline has finished and final_data_for_powerbi.json is generated, start the Streamlit dashboard:

Bash

streamlit run dashboard.py
Project Structure
run_pipeline.py: The master script that orchestrates the entire data flow.

dashboard.py: The Streamlit application for data visualization.

requirements.txt: List of Python library dependencies.

final_data_for_powerbi.json: The final enriched dataset used by the dashboard.

weather_data.csv: Historical weather records used for correlation.

terspegelt.json: Source review data.

Dashboard Insights
The dashboard allows users to filter data by year, topic, and period (Holiday vs. Off-season). It specifically highlights "Improvement Areas" by generating Word Clouds from negative reviews, allowing management to quickly identify recurring complaints.
