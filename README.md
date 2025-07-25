<div align="center">
<h1 style="color: #e9c46a; font-size: 3em; font-weight: bold;">
📊 Data-Driven Stock Analysis Dashboard
</h1>
</div>

This project provides a comprehensive Streamlit web application for analyzing stock market data, focusing on key performance metrics, volatility, sector-wise performance, and inter-stock correlations. It processes raw YAML data, transforms it into a usable format, and presents insights through interactive visualizations.

✨ Features
Automated Data Extraction & Transformation: Processes raw YAML stock data into structured CSV files for easier analysis.

Key Performance Metrics:

Calculates daily and yearly returns for all stocks.

Identifies and displays the Top 10 Best Performing (Green) and Worst Performing (Red) Stocks.

Provides a market summary including the number of green/red stocks and average prices/volumes.

Volatility Analysis: Determines and visualizes the Top 10 Most Volatile Stocks based on the standard deviation of daily returns.

Cumulative Return Over Time: Tracks and plots the cumulative returns for the Top 5 Performing Stocks.

Sector-wise Performance Analysis: Breaks down stock performance by industry sector, showing average yearly returns for each.

Stock Price Correlation: Visualizes the correlation between stock daily returns using a heatmap, helping identify co-moving stocks.

Monthly Gainers and Losers: Allows users to select a month and view the Top 5 Gainers and Losers for that specific period.

Interactive Web Dashboard: All analyses and visualizations are presented within a user-friendly Streamlit web application.

Customizable Aesthetics: Easily change the dashboard's background and text colors via simple CSS adjustments.

📁 Project Structure
secondproject/
├── 2023-10/                  # Directory for October 2023 YAML data files
│   └── 2023-10-XX.yaml
├── 2023-11/                  # Directory for November 2023 YAML data files
│   └── 2023-11-XX.yaml
├── stock_data_csvs/          # (Generated) Directory for individual stock CSVs
│   └── ADANIENT.csv
│   └── RELIANCE.csv
│   └── ...
├── Sector_data - Sheet1.csv  # CSV file containing stock symbols and their sectors
├── .gitignore                # Specifies files/directories to ignore in Git
├── app.py                    # The main Streamlit web application script
├── analyze_data.py           # (Older) Standalone script for analysis (logic moved to app.py)
├── extract_data.py           # Script to extract data from YAMLs and convert to CSVs
└── requirements.txt          # Lists all Python dependencies

🚀 Setup and Installation
Follow these steps to set up and run the project locally:

Prerequisites
Python 3.8+: Download and install from python.org.

Git: Download and install from git-scm.com.

Steps
Clone the Repository:
Open your command prompt or terminal and clone the project:

git clone https://github.com/akashBv6680/secondproject.git
cd secondproject

Create a Virtual Environment:
It's highly recommended to use a virtual environment to manage dependencies.

python -m venv venv

Activate the Virtual Environment:

On Windows:

.\venv\Scripts\activate

On macOS/Linux:

source venv/bin/activate

(You should see (venv) at the beginning of your command prompt line, indicating the environment is active.)

Install Dependencies:
Install all required Python libraries using the requirements.txt file:

pip install -r requirements.txt

📊 Data Preparation
Your project uses stock data in YAML format (e.g., in 2023-10/ and 2023-11/ folders) and a Sector_data - Sheet1.csv file.

Extract Stock Data from YAMLs:
The extract_data.py script will read your YAML files and convert them into individual CSV files for each stock, saving them in the stock_data_csvs/ directory.

python extract_data.py

(Ensure your YAML data files are correctly placed in 2023-10/, 2023-11/, etc., within your secondproject directory).

Prepare Sector_data - Sheet1.csv:
This is a crucial manual step for accurate sector analysis.

Open Sector_data - Sheet1.csv in a spreadsheet editor (like Microsoft Excel).

Symbol Column (e.g., Column C): Ensure this column contains only the exact ticker symbol for each stock (e.g., ADANIENT, RELIANCE, TCS). Remove any company names or extra text.

sector Column (e.g., Column B): Ensure this column contains meaningful and consistent industry categories for each stock (e.g., Financials, IT, Energy, Automobiles, Healthcare, Industrials, Consumer Discretionary, Consumer Staples, Metals & Mining, Telecommunications, Utilities, Materials). Avoid generic terms like MISCELLANEOUS or company-specific terms.

Save the file as CSV (Comma delimited) (*.csv).

▶️ How to Run the Dashboard Locally
After completing the setup and data preparation:

Ensure your virtual environment is active.

Run the Streamlit application:

streamlit run app.py

This command will open a new tab in your default web browser, displaying your interactive stock analysis dashboard.

☁️ Deployment to Streamlit Community Cloud
To share your dashboard with others, you can deploy it for free using Streamlit Community Cloud.

Ensure GitHub Repository is Up-to-Date:
All your project files (app.py, extract_data.py, Sector_data - Sheet1.csv, 2023-10/, 2023-11/, stock_data_csvs/, .gitignore, requirements.txt) must be pushed to your GitHub repository (https://github.com/akashBv6680/secondproject).

Important: Verify your .gitignore file correctly excludes the venv/ folder.

To push your latest changes:

git add .
git commit -m "Updated app.py and added README"
git push origin main # Or 'master' if that's your branch name

Go to Streamlit Community Cloud:

Visit https://share.streamlit.io/

Log in with your GitHub account.

Deploy a New App:

Click "New app".

Select your repository (akashBv6680/secondproject), choose the correct branch (main), and set the main file path to app.py.

Click "Deploy!".

Streamlit will then build and deploy your application, providing you with a public URL.

🎨 Customization
Background Colors: To change the dashboard's background color, edit the background-color hex codes in the <style> block at the beginning of app.py. You can also adjust header and text colors for contrast.

Plot Colors: Matplotlib and Seaborn offer various color palettes (cmap for heatmaps, color for bars). Refer to their documentation for more options.

