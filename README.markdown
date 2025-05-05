# eDNA Species Classification and Analysis

This repository contains a collection of Jupyter notebooks for analyzing environmental DNA (eDNA) data, focusing on species classification, feature importance, integration of climatic data, and exploratory data analysis (EDA). The project leverages machine learning models and geospatial analysis to study marine species distributions and their relationships with environmental factors.

## Table of Contents
- [Project Overview](#project-overview)
- [Repository Structure](#repository-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Notebooks Description](#notebooks-description)
- [Data](#data)
- [Contributing](#contributing)
- [License](#license)

## Project Overview
The goal of this project is to analyze eDNA data to classify marine species and understand their ecological patterns. Key tasks include:
- Training machine learning models (Random Forest, Gradient Boosting, XGBoost, etc.) for species classification.
- Performing feature importance analysis using SHAP.
- Integrating climatic data (e.g., temperature) with species occurrence data.
- Conducting exploratory data analysis to visualize species diversity, co-occurrence, and distribution patterns.

## Repository Structure
```
├── eda-on-edna-data.ipynb           # Exploratory data analysis and visualization
├── integration-of-climatic-data.ipynb # Integration of climatic data with species occurrences
├── model-training.ipynb             # Machine learning model training and evaluation
├── shap-analysis.ipynb              # SHAP analysis for feature importance
├── README.md                        # Project documentation
└── requirements.txt                 # Python dependencies
```

## Installation
To run the notebooks, you need Python 3.11 and the required libraries. Follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/edna-species-analysis.git
   cd edna-species-analysis
   ```

2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Install Jupyter Notebook:
   ```bash
   pip install jupyter
   ```

## Usage
1. Start Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

2. Open the desired notebook (e.g., `model-training.ipynb`) in the Jupyter interface.

3. Update the dataset path in the notebooks to point to your local copy of the eDNA dataset (e.g., `edna new merged data.xlsx`).

4. Run the cells in the notebook to execute the analysis or model training.

## Notebooks Description
1. **model-training.ipynb**:
   - Trains multiple machine learning models (Random Forest, Gradient Boosting, XGBoost, LightGBM, etc.) for species classification.
   - Preprocesses data using SMOTE for class imbalance, k-mer extraction, and PCA for dimensionality reduction.
   - Evaluates models with cross-validation and classification reports.

2. **shap-analysis.ipynb**:
   - Performs SHAP (SHapley Additive exPlanations) analysis to interpret feature importance in the Random Forest model.
   - Visualizes feature contributions using summary plots.

3. **integration-of-climatic-data.ipynb**:
   - Integrates temperature data from GeoTIFF files with species occurrence data using geospatial analysis.
   - Visualizes species density and richness with heatmaps and KDE plots.

4. **eda-on-edna-data.ipynb**:
   - Conducts exploratory data analysis on the eDNA dataset.
   - Generates visualizations such as species diversity across environmental scales, primer effectiveness, species co-occurrence networks, and latitudinal diversity patterns.

## Data
The project uses the eDNA dataset (`edna new merged data.xlsx`) and high-resolution GeoTIFF images of climatic data. Key columns in the dataset include:
- `scientificName`: Target variable for species classification.
- `decimalLatitude`, `decimalLongitude`: Geospatial coordinates.
- `DNA_sequence`: Sequence data for k-mer extraction.
- `env_broad_scale`, `target_gene`, `pcr_primer_name_forward`: Categorical features.

**Note**: Due to the size of the dataset and GeoTIFF files, they are not included in the repository. Users must provide their own copies and update the file paths in the notebooks.

## Contributing
Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes and commit (`git commit -m "Add new feature"`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

Please ensure your code follows PEP 8 style guidelines and includes appropriate documentation.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.