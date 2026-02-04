# Bioactivity Prediction Project - Drug Discovery Pipeline

This repository contains the first two phases of a computational drug discovery project aimed at predicting the bioactivity of small molecules against a target protein using Machine Learning.

## 📌 Project Overview
The goal of this project is to identify potential drug candidates by analyzing bioactivity data. We move from raw chemical data to a cleaned, feature-rich dataset ready for model building.

- **Part 1:** Data Collection and Preprocessing from the ChEMBL database.
- **Part 2:** Exploratory Data Analysis (EDA) and Molecular Descriptor Calculation.

## 🧬 Phase 1: Data Collection
In this phase, we:
1.  Extracted bioactivity data for our target protein from the **ChEMBL Database**.
2.  Preprocessed the data by handling missing values and labeling compounds as **active**, **inactive**, or **intermediate** based on $IC_{50}$ thresholds.
3.  Cleaned the chemical SMILES strings for downstream processing.

## 📊 Phase 2: Exploratory Data Analysis (EDA)
Using **RDKit**, we calculated molecular descriptors to evaluate the "drug-likeness" of the compounds based on **Lipinski's Rule of Five**:

[Image of Lipinski's Rule of Five criteria]

* **Molecular Weight (MW):** < 500 Da
* **Octanol-water partition coefficient (LogP):** < 5
* **Hydrogen Bond Donors:** < 5
* **Hydrogen Bond Acceptors:** < 10

### Data Transformations
To prepare the data for statistical analysis, we performed:
* **Normalization:** Capping $IC_{50}$ values to 100,000,000 nM to handle outliers.
* **pIC50 Conversion:** Transforming $IC_{50}$ to a negative logarithmic scale ($pIC_{50}$) for a more uniform distribution.

[Image of distribution plot of pIC50 values]

## 🛠️ Tools & Libraries
* **RDKit:** For cheminformatics and molecular descriptor calculation.
* **Pandas/NumPy:** For data manipulation and transformation.
* **Seaborn/Matplotlib:** For visualizing chemical space and bioactivity distributions.
* **Scipy:** For statistical significance testing (Mann-Whitney U test).

## 🚀 How to Run
The notebooks are designed to run in **Google Colab**. 
To install the necessary dependencies, run:
```python
pip install rdkit pandas seaborn numpy
```

📈 Next Steps
[ ] Part 3: Feature Engineering using PaDEL-Descriptor (Molecular Fingerprints).

[ ] Part 4: Regression Model Building (Comparing Random Forest, SVM, etc.).

[ ] Part 5: Model Deployment via Streamlit.
