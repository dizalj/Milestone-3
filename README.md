# ML Pipeline Development - Milestone 3
This milestone focuses on transforming raw ingredient substitution data into a structured and versioned dataset using an ML pipeline. The pipeline was implemented in **Google Colab** with **ZenML**, **DVC**, **MongoDB**, and **Feast** for scalable feature storage. The goal was to establish a reproducible and modular data pipeline that ensures high-quality data preparation.

### **Key Achievements**

- **Schema Definition:**
  - Defined a structured schema for ingredient substitution data.
  - Standardized column names (`Ingredient`, `Substitute`, `Context`, `Equivalent`).

- **Data Validation and Verification:**
  - Checked schema consistency and handled missing values.

- **Data Versioning:**
  - Implemented **DVC with Google Drive remote storage** to track dataset versions.

- **Setting Up a Feature Store:**
  - Integrated **Feast** as a feature store.
  - Defined `ingredient_id` as a unique entity.
  - Stored embeddings for `Ingredient` and `Substitute` using `SentenceTransformers`.

---

## **Setup of the Data Pipeline**

### **Ingestion of Raw Data and Storage into a Repository**
- Connected to **MongoDB** to store raw ingredient data.
- Loaded the dataset into a **Pandas DataFrame** for preprocessing.

### **Preprocessing and Feature Engineering**
- Converted **text to embeddings** using `all-MiniLM-L12-v2` from `SentenceTransformers`.
- **Extracted numeric values** from `Equivalent` column (e.g., `1 cup` → `1.0`, `cup`).
- Normalized ingredient names and removed extra whitespace.

For more details, see the **[Milestone3.ipynb](./Milestone3.ipynb)** notebook.

---

## **📂 Repository Structure**
- **Milestone3.ipynb:** Full pipeline implementation (ingestion, preprocessing, validation, feature engineering, and versioning).
- **substitutes.csv:** The dataset used for processing.
- **feature_store.yaml:** Feast configuration file for the feature store.
- **laddaty_feature_repo/**: Contains the registry and stored features.

---

This structured pipeline enables **scalable and reproducible ML workflows** for ingredient substitution data.
