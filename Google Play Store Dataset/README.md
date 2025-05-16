# 📱 Google Play Store Data Cleaning, EDA, and Feature Engineering

This repository contains a complete data cleaning, exploration, and feature engineering pipeline for the [Google Play Store dataset](https://www.kaggle.com/lava18/google-play-store-apps). The dataset includes metadata for over 10,000 Android applications.

---

## 🗂 Dataset Overview

The dataset includes the following columns:

- `App`: Application name
- `Category`: Category the app belongs to
- `Rating`: Overall user rating
- `Reviews`: Number of user reviews
- `Size`: Size of the app
- `Installs`: Number of installs
- `Type`: Free or Paid
- `Price`: Price of the app
- `Content Rating`: Age group targeted
- `Genres`: App genre(s)
- `Last Updated`: Date when the app was last updated
- `Current Ver`: Current version of the app
- `Android Ver`: Minimum Android version required

---

## 🔧 Steps Performed

### 1️⃣ Data Cleaning

Performed comprehensive cleaning on messy and inconsistent data:

- **`Reviews`**: Removed non-numeric entries and converted to integers.
- **`Size`**: Replaced 'M', 'k', and 'Varies with device', then converted to float (in kilobytes).
- **`Installs`**: Removed '+' and ',' then converted to integer.
- **`Price`**: Removed dollar signs and converted to float.
- **`Last Updated`**: Converted to `datetime`, extracted `day`, `month`, and `year` as separate features.

---

### 2️⃣ Exploratory Data Analysis (EDA)

Performed insightful EDA to understand trends, outliers, and correlations:

- **Rating Distribution**: Used histograms and KDE plots to observe how app ratings are distributed.
- **Category Popularity**: Countplot to show number of apps in each category.
- **Installs vs Rating**: Analyzed whether higher installs lead to better ratings.
- **Price Analysis**: Compared paid vs free apps using box plots.
- **Review Counts**: Visualized distribution of reviews across different app types and categories.
- **Size vs Installs**: Investigated if app size has any impact on number of installs.

Visualization libraries used:
- `seaborn`
- `matplotlib`

---

### 3️⃣ Feature Engineering

Created new columns to enhance the dataset and support further analysis/modeling:

- `Last Updated Day`: Day extracted from `Last Updated`
- `Last Updated Month`: Month extracted from `Last Updated`
- `Last Updated Year`: Year extracted from `Last Updated`
- Future scope:
  - One-hot encoding for `Category`, `Genres`, and `Content Rating`
  - Grouping genres into broader categories
  - Generating a binary column for "popular app" based on threshold installs

## 🛠 Libraries Used

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
