# Used Car Price Prediction: Analysis for Inventory Strategy

## Project Overview
**Goal:** To analyze a dataset of used cars from Kaggle and determine the key factors that influence their pricing. 
**Client:** A used car dealership looking to fine-tune their inventory acquisition strategy.
**Framework:** This project follows the CRISP-DM (Cross-Industry Standard Process for Data Mining) methodology.

## Key Findings (Executive Summary)
Based on an analysis of over 400,000 vehicle listings and a Ridge Regression model (Accuracy: 67.5%), the following actionable insights were identified for the dealership:

1.  **Diesel is King:**
    *   The strongest positive driver of price is the **Diesel** engine. Compared to standard Gas engines, Diesel vehicles command a premium of roughly **$12,000**.
    *   *Action:* Prioritize the acquisition of diesel trucks and heavy-duty vehicles.

2.  **Body Type Matters:**
    *   **Trucks, Coupes, and Pickups** hold the highest value retention.
    *   Sedans and Hatchbacks are significantly lower in value.
    *   *Action:* Shift inventory mix toward utility (work) and sport (lifestyle) vehicles.

3.  **The "Brand" Trap (Electric Vehicles):**
    *   **Tesla** is the only electric brand with a strong positive price coefficient (+$29k).
    *   Generic electric/hybrid vehicles actually show a *negative* price impact compared to the baseline.
    *   *Action:* Be cautious with non-Tesla EVs; brand prestige is the primary driver of value in the EV sector.

4.  **Avoid High-Risk Inventory:**
    *   Vehicles with **"Salvage"** or **"Parts Only"** titles reduce value by over $5,000 immediately.
    *   Brands such as **Fiat, Mercury, and Chrysler** show the steepest depreciation curves.

## Methodology

### 1. Business Understanding
The objective was to identify the features (year, manufacturer, mileage, etc.) that have the highest correlation with price to guide dealers on what to stock.

### 2. Data Understanding & Preparation
*   **Source:** Kaggle Used Car Dataset.
*   **Cleaning:** Removed listings with prices $0 or >$100k, and odometers >300k miles.
*   **Feature Engineering:** Converted `cylinders` to numerical values; One-Hot Encoded categorical variables (`fuel`, `manufacturer`, `title_status`).

### 3. Modeling
Two models were evaluated:
*   **Baseline:** Linear Regression.
*   **Advanced:** Ridge Regression with GridSearchCV (Optimized Alpha: 1).

### 4. Evaluation
*   **Performance:** The model achieved an $R^2$ score of **0.675**, explaining 67.5% of the price variance.
*   **Error:** The Mean Absolute Error indicates predictions are typically within ~$7,900 of the actual listing price.

## Recommendations
To maximize profit margins, the dealership should:
1.  **Buy:** Diesel Pickups, Tesla models, and low-mileage Coupes.
2.  **Sell/Avoid:** Fiats, Chryslers, and vehicles with any title defects (Salvage/Rebuilt).
3.  **Pricing:** Expect a standard Gas Sedan to sell for approximately $12k less than a comparable Diesel Truck.

## Repository Structure
*   `data/`: Contains the dataset (if applicable/allowed).
*   `images/`: Saved visualizations from the analysis.
*   `prompt_II.ipynb`: The Jupyter Notebook containing the full analysis and code. [View Notebook Here](prompt_II.ipynb)

---
*Author: [Your Name]*
*Date: [Current Date]*
