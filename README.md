# dataops-company-info-gatherer

## Description

This is a simple tool to gather information about companies from their websites. It uses the `requests`, `beautifulsoup4`, and `selenium` libraries to scrape the data.

The tool can be used to gather the following information:
- Company name with latest news
- Company stock price changes
- Currency exchange rates evolution
- Scraping latest news articles using Selenium and Undetected ChromeDriver

## Contents
- [Project structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)

## Project structure
```
root/
│   src/
│   │   ..... # main scripts and modules
│   │   api_v2.py                       # Main script to fetch a stock price changes
│   │   webscraping_selenium.py         # Selenium-based web scraping script for news
│   │   webscraping_beautifulsoup.py    # BeautifulSoup-based web scraping script 
│   |
│   utils/
│   │   webdriver/
│   |
|   data/
│   │   currency_exchange_rate_{currency_from}_{currency_to}.csv
│   │   monthly_adjusted_time_series_{symbol}.csv
│   │   {keyword}_news.csv  # Scraped news data
|   |   ..... # data files generated by the scripts
│   |
│   |
│   .env
│   .env.example
│   .gitignore
│   README.md
│   requirements.txt
|
```

## Installation
1. Clone the repository

2. Install the required libraries
    ```bash
    pip install -r requirements.txt
    ```

3. Install the `chromedriver` for `selenium` to work. You can download it from [here](https://sites.google.com/a/chromium.org/chromedriver/downloads).

4. Copy the `chromedriver` to the `utils/webdriver` directory.

5. This tool uses `.env` files to store the environment variables. Create a copy of the `.env.example` file and rename it to `.env`. Fill in the required values.

## Usage

You can run the tool using the following list of commands:

> Fetch the company stock price changes and write the data to a CSV file
```bash
cd to_your_project_directory
python src/api_v2.py
# Follow prompt instructions
```

> Obtain the current currency exchange rate and add them to a CSV file
```bash
cd to_your_project_directory
python src/webscraping_beautifulsoup.py
# Follow prompt instructions
```

> Scrape the latest company news using Selenium
```bash
cd to_your_project_directory
python src/webscraping_selenium.py
# Follow prompt instructions to enter search keywords, start page, and max pages
```