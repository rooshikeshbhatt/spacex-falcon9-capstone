# SpaceX Falcon 9 Launch Analysis – Data Science Capstone

## Project Overview
This project analyzes **SpaceX Falcon 9 first-stage landing outcomes** using a complete data science workflow. The objective is to uncover patterns that influence landing success and to build predictive models that estimate the likelihood of a successful landing based on mission characteristics.

The project follows an end-to-end data science pipeline, covering data collection, data wrangling, exploratory data analysis, interactive visualization, and machine learning–based prediction.

---

## Objectives
- Analyze historical Falcon 9 launch data to understand landing success trends  
- Identify how mission parameters such as orbit type, payload mass, and launch site affect outcomes  
- Visualize insights using static and interactive analytics  
- Build and evaluate supervised classification models to predict landing success  

---

## Data Sources
Data was gathered from multiple complementary sources:

- **SpaceX REST API (v4)**  
  - `/launches/past`  
  - `rocket`, `launchpad`, `payloads`, and `cores` endpoints  

- **Web Scraping**  
  - Falcon 9 launch history tables from Wikipedia  

The SpaceX API provided structured mission metadata, while web scraping was used to supplement and validate historical launch information.

---

## Methodology

### 1. Data Collection
- Retrieved historical launch records using the SpaceX API  
- Backfilled related mission details using linked API endpoints  
- Scraped additional launch data from Wikipedia using BeautifulSoup  

### 2. Data Wrangling
- Cleaned and standardized column formats  
- Handled missing and inconsistent values  
- Converted mission outcomes into a binary **Class** label (success vs failure)  

### 3. Exploratory Data Analysis (EDA)
Performed exploratory analysis using Python visualizations and SQL queries to examine:
- Launch success trends over time  
- Success rates by launch site and orbit type  
- Payload mass distributions  
- Relationships between payload, orbit, and landing outcomes  

### 4. SQL Analysis
Key SQL queries included:
- Identifying unique launch sites  
- Calculating total and average payload mass  
- Determining the first successful ground landing date  
- Counting successful vs failed mission outcomes  
- Identifying booster versions carrying maximum payloads  

### 5. Interactive Visual Analytics
- Built **Folium maps** to explore geographical patterns of launch sites  
- Developed a **Plotly Dash dashboard** featuring:
  - Launch site selection via dropdown  
  - Interactive pie charts showing success distribution  
  - Scatter plots displaying payload mass vs outcome  
  - Payload mass range filtering  

### 6. Feature Engineering
- One-hot encoded categorical variables  
- Converted numerical features to `float64`  
- Selected relevant features for predictive modeling  

### 7. Predictive Analysis
Built and tuned multiple classification models using **GridSearchCV**:
- Logistic Regression  
- Support Vector Machine (SVC)  
- Decision Tree Classifier  
- K-Nearest Neighbors  

Data was standardized using `StandardScaler` and split into training and testing sets.

---

## Key Findings
- Landing success improved significantly over time, especially after 2015  
- **KSC LC-39A** demonstrated the highest overall landing success rate  
- **ES-L1, SSO, HEO, and GEO** orbits consistently achieved high success rates  
- **GTO missions** showed more variable and lower success due to higher mission complexity  
- Heavier payload missions initially experienced higher failure rates, but performance improved with technological advancements  

---

## Model Performance

| Model                | Test Accuracy |
|---------------------|---------------|
| Logistic Regression | 83.33%        |
| SVM                 | 83.33%        |
| KNN                 | 83.33%        |
| Decision Tree       | 77.78%        |

Logistic Regression, SVM, and KNN achieved the highest overall test accuracy.

---

## Tools & Technologies
- Python (Pandas, NumPy, Matplotlib, Seaborn)  
- Scikit-learn  
- SQL (SQLite)  
- BeautifulSoup (Web Scraping)  
- Folium (Interactive Maps)  
- Plotly Dash (Interactive Dashboard)  

---

## Repository Structure
```

├── notebooks/
│   ├── data_collection_api.ipynb
│   ├── data_collection_web_scraping.ipynb
│   ├── data_wrangling.ipynb
│   ├── eda_visualization.ipynb
│   ├── eda_sql.ipynb
│   ├── interactive_maps_folium.ipynb
│   ├── predictive_analysis.ipynb
│
├── dashboard/
│   └── app.py
│
├── presentation/
│   └── SpaceX_Capstone_Presentation.pdf
│
├── README.md

```

---

## Conclusion
This project demonstrates how data science techniques can be applied to real-world aerospace challenges. By integrating historical data analysis, interactive visualization, and predictive modeling, meaningful insights were derived regarding Falcon 9 landing success. The results highlight the impact of experience, mission design, and orbit selection on successful booster recovery.

---
```
