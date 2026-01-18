# NBA 2018–2019 Season Analysis🏀🏀

![MIT License](https://img.shields.io/badge/license-MIT-green)

A comprehensive exploratory data analysis (EDA) of NBA player performance during the 2018–2019 season. This project examines detailed statistics for 150+ top players across all 30 teams, focusing on scoring efficiency, playmaking ability, rebounding metrics, and overall contribution patterns to identify standout performances and evaluate the impact of mid-season roster changes.

<br/>

## 📍*The `NBA_Eda.ipynb` notebook is too large to be displayed. Just download it locally and upload to your `Google Drive` to use colab virtual environment*

---

## Table of Contents
* [Overview](#overview)
* [Technical Highlights](#technical-highlights)
* [Installation](#installation)
* [Usage](#usage)
* [Libraries and Technologies](#libraries-and-technologies)
* [Dataset](#dataset)
* [Analysis Workflow](#analysis-workflow)
* [Key Features](#key-features)
* [License](#license)
* [Contributing](#contributing)
* [Questions](#questions)

<br/>

## Overview

This project performs in-depth statistical analysis of NBA player performance metrics from the 2018–2019 regular season. The analysis explores relationships between various performance indicators including points, assists, rebounds, shooting percentages, and playing time to uncover patterns that distinguish elite performers from role players.

The notebook implements professional data science methodologies including automated data profiling, multi-dimensional quality validation, statistical outlier detection, and interactive visualization techniques to extract actionable insights from player statistics.

<br/>

## Technical Highlights

The analysis demonstrates advanced data science techniques and best practices:

* **Automated Data Profiling**: Leverages `ydata-profiling` library to generate comprehensive statistical reports with correlation matrices, distribution analyses, and data quality assessments
* **Statistical Outlier Detection**: Implements Interquartile Range (IQR) methodology to identify anomalous values while preserving legitimate variance across different player archetypes and usage patterns
* **Feature Normalization**: Applies z-score standardization via `scipy.stats.zscore` to enable fair comparison of metrics measured on different scales
* **Interactive Visualization**: Combines Plotly's interactive capabilities with Matplotlib and Seaborn's statistical graphics for multi-layered data exploration
* **Correlation Analysis**: Employs multi-variate heatmaps and scatter plot matrices to identify significant relationships between performance metrics
* **Data Quality Framework**: Implements seven-point validation covering reliability, timeliness, consistency, relevance, uniqueness, completeness, and accuracy

<br/>

## Installation

### Prerequisites
* Google Account (for Google Colab)
* Web browser with internet connection

### Setup Instructions

**1: Google Colab (Recommended)**

1. Open the notebook directly in Google Colab:
   - Navigate to [Google Colab](https://colab.research.google.com/)
   - Click `File > Upload notebook`
   - Upload `NBA_Eda.ipynb` or connect to GitHub and import directly

2. All dependencies are installed automatically within the notebook, including:
   ```python
   !pip install ydata-profiling
   ```

3. No additional setup required - all libraries (Pandas, NumPy, Matplotlib, Seaborn, Plotly) are pre-installed in Colab

<br/>

## Usage

### Running the Analysis in Google Colab

1. Upload `NBA_Eda.ipynb` to Google Colab or open directly from GitHub

2. Execute cells sequentially using `Shift + Enter` or run all cells via `Runtime > Run all`

3. The notebook will automatically:
   - Install `ydata-profiling` using pip
   - Load the dataset from Hugging Face
   - Execute all analysis steps
   - Generate interactive visualizations

4. Interactive Plotly charts will render directly in the notebook with full functionality (zoom, pan, hover tooltips)

### Analysis Outputs

The notebook generates:
* Automated profiling report with comprehensive statistical summaries
* Distribution plots for all key performance metrics
* Correlation heatmaps revealing relationships between variables
* Interactive scatter plots for bivariate analysis
* Box plots identifying outliers and quartile distributions
* Summary statistics tables for categorical groupings (by team, position, etc.)

<br/>

## Libraries and Technologies

### Core Data Science Stack
* **Pandas** - Data manipulation, transformation, and aggregation
* **NumPy** - Numerical computing and array operations
* **SciPy** - Statistical functions including z-score calculations and hypothesis testing

### Visualization Suite
* **Plotly Express** - High-level interface for interactive charts
* **Plotly Graph Objects** - Low-level API for complex multi-trace visualizations
* **Matplotlib** - Foundational plotting library for static graphics
* **Seaborn** - Statistical visualization with enhanced aesthetics

### Data Profiling
* **ydata-profiling** - Automated exploratory data analysis report generation (installed via notebook)

**Note**: All libraries except `ydata-profiling` come pre-installed in Google Colab. The notebook includes the necessary pip install command for `ydata-profiling`.

<br/>

## Dataset

### Source
* **Primary**: [NBA Players Results 2018](https://huggingface.co/datasets) via Hugging Face
* **Validation**: Cross-referenced with ESPN NBA Stats and Basketball Reference for accuracy verification

### Dataset Characteristics
* **Rows**: 150+ players (top performers by minutes played)
* **Columns**: 29 statistical features
* **Time Period**: 2018–2019 NBA Regular Season
* **Update Frequency**: Season-end snapshot with mid-season trade adjustments

### Feature Categories

**Player Information**
* Rank, Name, Age, Team, Position

**Usage Metrics**
* Games (G), Games Started (GS), Minutes Per Game (MP)

**Shooting Statistics**
* Field Goals: Made/Attempted/Percentage (FG, FGA, FG%)
* Three-Pointers: Made/Attempted/Percentage (3P, 3PA, 3P%)
* Free Throws: Made/Attempted/Percentage (FT, FTA, FT%)

**Performance Indicators**
* Scoring: Points Per Game (PTS/G)
* Rebounding: Offensive/Defensive/Total (ORB, DRB, TRB)
* Playmaking: Assists (AST), Turnovers (TOV)
* Defense: Steals (STL), Blocks (BLK)
* Discipline: Personal Fouls (PF)

<br/>

## Analysis Workflow

The notebook follows a systematic analytical pipeline:

### 1. Data Profiling
Automated generation of comprehensive statistical reports using `ydata-profiling`, including:
* Univariate distributions and summary statistics
* Correlation matrices and interaction effects
* Missing value patterns and data types
* Duplicate detection and anomaly flags

### 2. Data Quality Assessment
Seven-point validation framework:
* **Reliability**: Source verification and data consistency checks
* **Timeliness**: Verification of season-appropriate data
* **Consistency**: Format standardization and type validation
* **Relevance**: Feature selection based on analytical objectives
* **Uniqueness**: Duplicate identification and resolution
* **Completeness**: Missing value analysis and imputation strategies
* **Accuracy**: Cross-validation with official NBA statistics

### 3. Data Cleaning
* Handling missing values (particularly 3P% for non-shooters)
* Managing duplicate records from mid-season trades (retaining youngest age)
* Type conversions and format standardization
* Outlier identification while preserving legitimate variance

### 4. Univariate Analysis
Individual variable exploration through:
* Histograms showing distribution shapes
* Box plots revealing quartiles and outliers
* Frequency tables for categorical variables
* Measures of central tendency and dispersion

### 5. Bivariate & Multivariate Analysis
Relationship exploration via:
* Correlation heatmaps quantifying linear relationships
* Scatter plots with trend lines
* Grouped statistics by team and position
* Multi-dimensional pattern recognition

<br/>

## Key Features

### Robust Data Handling
* **Mid-Season Trades**: Automatically handles players who changed teams by preserving the record with the youngest age (typically representing the longer tenure)
* **Missing Value Strategy**: Distinguishes between true missing data and structural zeros (e.g., 0.0 for 3P% when 3PA = 0)
* **Outlier Preservation**: Retains statistical outliers that represent legitimate elite performance rather than data errors

### Statistical Rigor
* IQR-based outlier detection with contextual interpretation
* Z-score normalization for cross-metric comparisons
* Correlation analysis with significance testing
* Distribution fitting and normality assessments

### Visualization Quality
* Interactive Plotly charts with hover tooltips and zoom capabilities
* Publication-ready static graphics with clear annotations
* Consistent color schemes and professional formatting
* Multi-panel layouts for comparative analysis

<br/>

## License

This project is licensed under the [MIT License](https://choosealicense.com/licenses/mit/).

You are free to use, modify, and distribute this software for personal or commercial purposes. See the LICENSE file for full details.

<br/>

## Contributing

Contributions are welcome and encouraged! To contribute:

1. **Open an Issue**: Describe your proposed enhancement or bug fix in the GitHub Issues section
2. **Fork the Repository**: Create your own copy to work on changes
3. **Submit a Pull Request**: Once your changes are tested, submit a PR with a clear description

Areas particularly welcome for contribution:
* Additional statistical tests and analyses
* Integration of advanced player metrics (PER, VORP, Win Shares)
* Comparative analysis across multiple seasons
* Machine learning models for performance prediction
* Enhanced visualizations and dashboard creation

For questions or collaboration discussions, contact via email below.

<br/>

## Questions

For questions, suggestions, or collaboration opportunities:

**GitHub**: [YasserAlbogami](https://github.com/YasserAlbogami)  
**Email**: yasserayalbogami@gmail.com
