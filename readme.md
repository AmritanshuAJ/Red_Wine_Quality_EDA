# Red Wine Quality EDA (Red Vinho Verde)

This repository contains an Exploratory Data Analysis (EDA) of the Red Wine Quality dataset, specifically focusing on red variants of the Portuguese "Vinho Verde" wine. The analysis aims to understand the physicochemical properties of red wines and identify features that influence their perceived quality, laying the groundwork for potential regression or classification models.

## Table of Contents

- [About The Project](#about-the-project)
- [Dataset](#dataset)
- [Exploratory Data Analysis (EDA) Highlights](#exploratory-data-analysis-eda-highlights)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Built With](#built-with)
- [Project Structure](#project-structure)
- [Contact](#contact)
- [Acknowledgments](#acknowledgments)

## About The Project

This project performs an in-depth Exploratory Data Analysis (EDA) on the Red Wine Quality dataset. The primary goals are:

- To understand the distribution and characteristics of various physicochemical properties of red wine.
- To identify which of these features have a significant influence on the wine's perceived quality.
- To prepare the dataset for future machine learning applications, such as predicting wine quality (regression) or classifying wines as 'good'/'not good' (binary classification).

The notebook covers:

- Initial data loading and inspection (`.head()`, `.info()`, `.describe()`).
- Handling of duplicate records.
- Analysis of target variable distribution (quality).
- Correlation analysis through heatmaps to understand relationships between features and with the target variable.
- Univariate, bivariate, and multivariate observations to uncover patterns and potential outliers.

## Dataset

The dataset used in this analysis is the "Wine Quality dataset," focusing specifically on red wines. It was originally sourced from the UCI Machine Learning Repository and conveniently made available on Kaggle.

**Source Link:** [UCI Machine Learning Repository: Wine Quality Dataset](https://archive.ics.uci.edu/ml/datasets/wine+quality)

**Citation (for academic use):**
> P. Cortez, A. Cerdeira, F. Almeida, T. Matos and J. Reis. Modeling wine preferences by data mining from physicochemical properties. Decision Support Systems, Elsevier, 47(4):547-553, 2009.

### Variables

The dataset comprises 11 input features (physicochemical properties) and 1 output variable (quality rating from 0 to 10).

#### Physicochemical (Input) Variables:

- **Fixed acidity** (g/dm³) – Tartaric acid content.
- **Volatile acidity** (g/dm³) – Acetic acid content.
- **Citric acid** (g/dm³) – Citric acid content.
- **Residual sugar** (g/dm³) – Amount of sugar remaining after fermentation.
- **Chlorides** (g/dm³) – Salt content.
- **Free sulfur dioxide** (mg/dm³) – Free form of SO₂.
- **Total sulfur dioxide** (mg/dm³) – Total amount of SO₂.
- **Density** (g/cm³) – Density of the wine.
- **pH** – Acidity/basicity.
- **Sulphates** (g/dm³) – Sulphate content.
- **Alcohol** (% vol) – Alcohol content.

#### Output Variable:

- **Quality** – Wine quality score (integer: 0–10) based on sensory data.

## Exploratory Data Analysis (EDA) Highlights

The EDA revealed several key insights:

**Dataset Structure:** The dataset contains 1599 entries and 12 columns. After removing duplicates, 1359 unique entries remain. No missing values were found, indicating a clean dataset.

**Quality Distribution:** The quality variable shows an imbalanced distribution, with most wines rated between 5 and 6. A small fraction of wines are rated below 4 or above 7, indicating moderate class imbalance that must be handled during modeling.

**Univariate Observations:** Most continuous features are right-skewed and would benefit from normalization or standardization. Some variables such as residual sugar and sulphates show potential outliers.

**Correlation Analysis:**
- `alcohol` shows the strongest positive correlation with quality (approximately 0.48).
- `volatile acidity` has a moderate negative correlation with quality (approximately -0.39).
- `citric acid` and `sulphates` also demonstrate weaker but meaningful positive correlations.
- Some features like `density` and `pH` exhibit very low correlation with quality.

**Bivariate and Multivariate Insights:** Higher alcohol content generally corresponds with better wine quality. Wines with lower volatile acidity tend to have higher quality scores. Multivariate visualizations show partial separation of wine classes based on alcohol and acidity-related features, suggesting these will be valuable predictors.

## Getting Started

To run this analysis locally or on Google Colab, follow these steps.

### Prerequisites

Ensure you have Python installed (preferably Python 3.x). You will also need pip for package installation for local execution.

- **Python 3.x**
  ```bash
  # Check Python version
  python --version
  ```

- **pip (Python package installer)**
  ```bash
  # Ensure pip is installed
  python -m ensurepip --upgrade
  ```

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your_username/your_project.git
   # Replace 'your_username/your_project' with your actual repository path.
   ```

2. **Navigate into the project directory:**
   ```bash
   cd your_project_name # Replace with your project directory name
   ```

3. **Install the required Python packages (for local execution):**
   
   The notebook uses pandas, numpy, matplotlib, and seaborn. You can install them using pip:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```

   Alternatively, if a `requirements.txt` file is present (recommended for projects):
   ```bash
   pip install -r requirements.txt
   ```

## Usage

To view and interact with the EDA:

### Open the Jupyter Notebook locally:

If running locally, navigate to the project directory in your terminal and run:
```bash
jupyter notebook Red_Wine_Quality.ipynb
```

This command will open the Jupyter interface in your web browser, from where you can navigate to and open `Red_Wine_Quality.ipynb`.

### Open on Google Colab:

Alternatively, you can open this notebook directly in Google Colab for an environment with pre-installed dependencies and cloud execution.

1. Go to [Google Colab](https://colab.research.google.com/).
2. Click on "File" > "Upload notebook" and select `Red_Wine_Quality.ipynb` from your cloned repository.
3. Alternatively, you can open it directly from GitHub by going to "File" > "Open notebook" > "GitHub" and pasting the URL to the `Red_Wine_Quality.ipynb` file in your repository.

### Run the cells:

Execute the cells sequentially to see the data loading, preprocessing, and all the exploratory data analysis steps, including visualizations.

## Built With

- **Python**
- **Pandas** - For data manipulation and analysis.
- **NumPy** - For numerical operations.
- **Matplotlib** - For data visualization.
- **Seaborn** - For statistical data visualization.
- **Jupyter Notebook** - For interactive analysis and presentation (can be run locally or on Google Colab).

## Project Structure

The project structure for this data analysis project is:

```
├── Data/
│   └── winequality-red.csv      # The raw dataset
├── Notebooks/
│   └── Red_Wine_Quality.ipynb   # Jupyter notebook for EDA (designed to run on Google Colab or locally)
├── images/
│   └── screenshot.png           # Optional: Screenshots/visuals for README
├── README.md                    # This README file
└── requirements.txt             # List of Python dependencies
```

### Explanation of directories and files:

- **data/**: This directory holds all the raw and processed data used in the project. Keeping data separate from code is good practice.
- **notebooks/**: Contains the Jupyter notebooks used for analysis, experimentation, or reporting.
- **images/**: (Optional) Stores any images, screenshots, or GIFs used in the README or other documentation.
- **README.md**: The main documentation file for your project, providing an overview and instructions.
- **requirements.txt**: Lists all the Python libraries and their versions required to run the project, making it easy for others to set up the environment.


## Contact

**Your Name/GitHub Profile:** [https://github.com/AmritanshuAJ](https://github.com/AmritanshuAJ)

## Acknowledgments

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php) for providing the dataset.
- [Kaggle](https://www.kaggle.com/) for making the dataset easily accessible.
- P. Cortez et al. for their original research on wine preferences.
- [Google Colab](https://colab.research.google.com/) for providing a convenient environment for notebook execution.
