# Land-Use-Research-Project-

# 🌍 Mapping Soil Erosion in Europe: Land Degradation Assessment via Gamma-Ray Spectroscopy and Remote Sensing

## Project Overview

This repository contains the code and documentation for a high-accuracy, cost-effective methodology to map land degradation risk across Western Europe. This research addresses the urgent global environmental challenge of soil erosion, particularly in European soils compromised by intensifying climate patterns (drought and erosive rainfall).

The innovative approach combines **Google Earth Engine (GEE)**, **Remote Sensing**, and **Machine Learning** to provide a dependable, non-conventional alternative to expensive field surveys for soil erosion monitoring.

---

## 💡 Key Highlights & Scientific Contribution

* **Novel Erosion Indicator:** Leverages spatial variations in **Cesium-137 ($^{137}\text{Cs}$)**, a radionuclide derived from gamma-ray spectrometry, as the primary and most influential indicator of soil erosion magnitude within the topsoil layer ($\sim 30\text{ cm}$).
* **Technology Stack:** The entire workflow is executed on **Google Earth Engine (GEE)**, a cloud-computing platform, allowing for planetary-scale geospatial analysis.
* **Machine Learning Model:** A **Random Forest Classifier** was trained and calibrated to predict land degradation rates.
* **High Accuracy:** The model achieved an **Overall Accuracy of 84.1%** and a **Kappa Index of $0.795$**, surpassing many conventional methods.
* **Global Applicability:** This approach offers a more time and cost-efficient tool, particularly beneficial for countries with limited resources for traditional soil surveys.

### Model Performance (Confusion Matrix)

The model's ability to correctly classify erosion rates across six classes is summarized in the table below:

| Class | Consumer’s Accuracy | Producer’s Accuracy |
| :--- | :--- | :--- |
| **Very Low** | $83.0\%$ | $89.2\%$ |
| **Low** | $81.7\%$ | $73.4\%$ |
| **Moderate** | $76.8\%$ | $73.7\%$ |
| **High** | $86.5\%$ | $85.6\%$ |
| **Very High** | $82.8\%$ | $85.0\%$ |
| **Extreme** | $86.6\%$ | $87.7\%$ |
| **Overall Accuracy** | **$84.1\%$** | |
| **Kappa Index** | **$0.795$** | |

---

## 📊 Methodology Summary

### 1. Data Collection & Feature Importance

The primary variable is Cesium-137 ($^{137}\text{Cs}$) spatial distribution (acquired via gamma-ray spectrometry) from the **European Soil Data Center (ESDC)**.

Auxiliary features (Slope, Aridity Index, Crop Cover) were selected based on **Random Forest Feature Importance** (Mean Decrease in Impurity - MDI), confirming Cesium-137 as the most influential feature.

| Feature | Importance Score |
| :--- | :--- |
| **Cesium-137 Rate** | **Highest** |
| **Slope** | High |
| **Aridity Index** | High |
| **Crop Cover** | High |
| *Other Soil Properties* | Lower |

### 2. Preprocessing and Classification

* **Region of Interest (ROI):** France, Belgium, and Luxembourg. 
* **Data Uniformity:** Geospatial datasets were resampled to a consistent **$\sim 900\text{ meter}$** spatial resolution.
* **Normalization:** Min-Max Normalization was applied to scale data to a standardized range of $0 \text{ to } 1$.
* **Classification:** The Random Forest Classifier was tuned using **Random Grid Search**, identifying the optimal configuration:
    * **$n\_\text{tree}$ (Number of Trees):** $60$
    * **$m\_\text{try}$ (Features per Split):** $4$
    * **Data Split:** $70\%$ for training, $30\%$ for testing/validation.

### 3. Final Erosion Rate Distribution

The final classification map shows a high risk of erosion across the region:

* **Very-Low Risk:** $2.13\%$
* **Low Risk:** $10.88\%$
* **Moderate Erosion:** $34.48\%$
* **High to Extreme Erosion:** **$42.01\%$** 

---

## 👩‍💻 Repository Structure and Access

The core of this research plan is implemented in JavaScript within the Google Earth Engine Code Editor.

| File/Code | Description |
| :--- | :--- |
| `random_forest_prediction.js` | The main script containing the Random Forest classifier implementation, feature definition, training, and final output generation. |

### Accessing the Code

The original code can be accessed through your Google Earth Engine repository:

* **Repository URL (for cloning):** `https://earthengine.googlesource.com/users/ee-landusepm/default` (Replace `ee-landusepm` with your alias if necessary).
* **GEE Code Editor:** Load the scripts directly from the "Owner" repository section.

### **Future Research Directions**

The next phase of this research will focus on moving beyond generalized solutions by classifying **specific types of land degradation** (e.g., water erosion, soil fertility decline) and developing unique, localized mitigation strategies for each affected plot of land.

---

## 🎓 Author Information

* **Author:** Prisha Malik
* **Affiliation:** Academy of Math Science and Engineering, United States of America
