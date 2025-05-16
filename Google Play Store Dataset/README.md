# 📱 Google Play Store Data Cleaning and Preprocessing

This repository contains a complete data cleaning and preprocessing pipeline for the [Google Play Store dataset](https://www.kaggle.com/lava18/google-play-store-apps). The dataset consists of metadata for 10,841 Android applications available on the Google Play Store.

## 📊 Dataset Overview

The dataset includes the following fields:

- App
- Category
- Rating
- Reviews
- Size
- Installs
- Type
- Price
- Content Rating
- Genres
- Last Updated
- Current Version
- Android Version

## 🧹 What This Code Does

This script performs the following major data cleaning and transformation tasks:

---

### 🔍 1. Initial Exploration

- Load the dataset using `pandas`.
- Display general information (`info`) and dataset shape.
- Identify missing values using `isnull().sum()`.

---

### 🧼 2. Cleaning `Reviews` Column

- Identify non-numeric values in the `Reviews` column.
- Remove rows with invalid data (like row index `10472`).
- Convert `Reviews` column to integer (`int`).

---

### 🧼 3. Cleaning `Size` Column

- Replace "M" with `000` to convert values like "3.0M" to "3000".
- Remove "k" from values like "500k".
- Replace "Varies with device" with `NaN`.
- Convert `Size` column to float.

---

### 🧼 4. Cleaning `Installs` and `Price`

- Remove special characters such as `+`, `,`, and `$`.
- Convert `Installs` to `int`.
- Convert `Price` to `float`.

---

### 🧼 5. Converting `Last Updated` to DateTime

- Parse the `Last Updated` column to datetime format using `pd.to_datetime()`.
- Extract `Day`, `Month`, and `Year` from the `Last Updated` column for time-based analysis.

---

## ✅ Final Cleaned DataFrame

After cleaning, the dataset contains:

- 10,840 entries and 16 columns
- Proper data types for numerical and datetime columns
- Missing values identified and partially handled
