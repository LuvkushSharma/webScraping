# Debarment Data Scraping, Entity Classification, and Analysis

## Project Overview

This project involves web scraping data from the Asian Development Bank (ADB) debarment list, predicting entity types (Person or Organization) using machine learning techniques, and performing exploratory data analysis (EDA) on the scraped data. The data is stored in a JSON format, and a CSV file is generated for further analysis.

## Table of Contents

- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
  - [1. Data Scraping](#1-data-scraping)
  - [2. Named Entity Recognition (NER)](#2-named-entity-recognition-ner)
  - [3. JSON and CSV Generation](#3-json-and-csv-generation)
  - [4. Exploratory Data Analysis (EDA)](#4-exploratory-data-analysis-eda)
- [Output Files](#output-files)
- [Results](#results)
- [Notes](#notes)
- [Contributors](#contributors)
- [License](#license)

## Technologies Used

- Python
- BeautifulSoup
- Requests
- spaCy
- JSON
- CSV
- VS Code

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/LuvkushSharma/webScraping.git
   cd webScraping
   ```

2. **Create a virtual environment:**

   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On Windows use `venv\Scripts\activate`
   ```

3. **Install the required packages:**

   ```bash
   pip install -r requirements.txt
   ```

## Usage

### 1. Data Scraping

The first step involves scraping the data from the specified URL, which contains a table of debarred persons and organizations.

- The web page is fetched using the `requests` library.
- The table data is extracted using `BeautifulSoup`.
- The "Other Name/Logo" column is ignored.

### 2. Named Entity Recognition (NER)

Using the spaCy library, named entities are extracted from the "Name" column to classify them as either a 'Person' or an 'Organization'.

- spaCy's `en_core_web_sm` model is utilized for NER.
- If an entity is classified as 'PERSON', it's labeled as a 'Person', otherwise as an 'Organization'.

### 3. JSON and CSV Generation

The cleaned and processed data is saved as `results.json` with additional keys:
- `uuid`: A unique ID for each record.
- `Entity Type`: The predicted entity type ('Person' or 'Organization').

The JSON file is then converted into CSV format for analysis.

### 4. Exploratory Data Analysis (EDA)

EDA is performed on the generated CSV data to explore various patterns and insights:
- Distribution of entity types.
- Debarment duration analysis.
- Nationality distribution.
- Sanction types and grounds for debarment.

## Output Files

- **results.json**: Contains the scraped and processed data in JSON format.
- **results.csv**: The JSON data converted into CSV format for analysis.

## Results

- Successfully scraped and classified 999 debarment records.
- Predicted the entity type for each entry using NER and heuristic methods.
- Conducted EDA to derive insights from the data.

## Notes

- The URL may occasionally be inaccessible. If that occurs, use the provided archived URL.
- The classification method relies on spaCy's pre-trained model and a simple heuristic for determining entity types. Accuracy may vary depending on the quality of the model.

## Contributors

- **Luvkush Sharma** - *Initial work* - [GitHub Profile](https://github.com/LuvkushSharma)

