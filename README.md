# Ethiopian Fintech Apps Review Analytics Pipeline

An automated data engineering and sentiment analysis pipeline designed to scrape, clean, evaluate, and categorize customer reviews for major mobile banking applications in Ethiopia. This project targets user feedback for the **Commercial Bank of Ethiopia (CBE)**, **Bank of Abyssinia (BoA)**, and **Dashen Bank** to extract operational business insights.

---

## 🚀 Pipeline Architecture

The project is structured as a modular, end-to-end data processing system:

1. **Data Collection (Task 1):** Connects to Google Play Store servers (Ethiopia region) to pull real-time reviews.
2. **Data Preprocessing (Task 1):** Cleans missing values, deduplicates repetitive entries, and normalizes date records.
3. **Sentiment Analysis (Task 2):** Passes cleaned text through a deep-learning Transformer network (`DistilBERT`) to assess user emotion.
4. **Topical Modeling (Task 2):** Groups reviews into actionable operational themes using an automated keyword matching engine.

---

## 📂 Project Directory Structure

```text
fintech-review-analytics/
├── .github/
│   └── workflows/
│       └── unittests.yml       # Automated CI/CD pipeline tests
├── data/
│   ├── processed/
│   │   └── enriched_reviews.csv # AI-processed data (Sentiment & Themes)
│   └── raw/
│       └── cleaned_reviews.csv  # Task 1 output (Cleaned raw scrapes)
├── notebooks/
│   └── exploration.ipynb        # Interactive Jupyter Notebook workspace
|   └── exploration.ipynb
├──tests/
    └──test_encironment.py
├── src/
│   ├── __init__.py
│   ├── database.py             # Database connector scripts
│   └── scraper.py              # Modular scraping script
├── .gitignore                  # Prevents CSV leakage to GitHub
├── README.md                   # Project documentation
└── requirements.txt            # Python dependencies