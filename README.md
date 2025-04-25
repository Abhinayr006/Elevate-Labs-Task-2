# Task 2: Exploratory Data Analysis (EDA) on Titanic Dataset

This repository contains the deliverables for Task 2 of the Elevate Labs internship, focusing on EDA of the cleaned Titanic dataset. The goal was to explore the dataset, identify patterns, trends, and anomalies (step 4), and make feature-level inferences from visualizations (step 5) to prepare for modeling in Task 3.

## Files

- **Notebook**:
  - `ElevateLabsTask-2.ipynb`: Jupyter Notebook containing the EDA code, including data loading, visualizations, and inference generation.

- **Data**:
  - `cleaned_titanic.csv`: Cleaned Titanic dataset (~718 rows, 9 columns: `Survived`, `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`, `Embarked_Q`, `Embarked_S`). Features are preprocessed (e.g., `Age` and `Fare` standardized, `Embarked` one-hot encoded).

- **Visualizations (Step 4)**:
  - `histograms.png`: Distributions of numerical features (`Age`, `Fare`, `SibSp`, `Parch`). Shows skewness (e.g., `Fare` is right-skewed) and outliers (e.g., high `SibSp` values).
  - `boxplots_numerical.png`: Boxplots of numerical features by `Survived`. Highlights trends (e.g., higher `Fare` for survivors) and outliers (e.g., extreme `Fare` values).
  - `pairplot.png`: Pairwise relationships between numerical features, colored by `Survived`. Reveals clusters (e.g., survivors with high `Fare`).
  - `correlation_matrix.png`: Heatmap of feature correlations. Shows strong relationships (e.g., `Pclass` negatively correlated with `Survived`, ~ -0.3 to -0.4).
  - `3d_scatter.html`: Interactive 3D scatter plot of `Age`, `Fare`, `Pclass`, colored by `Survived`. Saved as HTML due to `kaleido` 0.2.1 hanging on Python 3.13 during PNG export. Open in a browser to rotate/zoom and explore patterns (e.g., survivors cluster in `Pclass=1`, high `Fare`).
  - `categorical_plots.png`: Bar plots of survival by categorical features (`Pclass`, `Sex`, `Embarked_Q`, `Embarked_S`). Shows trends (e.g., females and first-class passengers have higher survival rates).

- **Inferences (Step 5)**:
  - `eda_inferences.txt`: Feature-level inferences derived from visualizations. Summarizes relationships (e.g., `Pclass`, `Sex`, `Fare` strongly predict survival), trends (e.g., younger passengers slightly more likely to survive), and anomalies (e.g., high `Fare` outliers often survive).

## Notes for Mentors
- The 3D scatter plot is provided as `3d_scatter.html` (not PNG) because `kaleido` 0.2.1, used for PNG export in Plotly, consistently hung on Python 3.13. Saving as HTML ensures reliability and offers interactivity (rotate/zoom in a browser) for better EDA insights.
- All visualizations and inferences are generated in `ElevateLabsTask-2.ipynb`. Cells are numbered and commented for clarity
- Survival rates in `eda_inferences.txt` (e.g., ~70-80% for females) are approximate, based on visualizations. Exact rates can be computed using `df.groupby('Sex')['Survived'].mean()` if needed.

## How to View
- Open `ElevateLabsTask-2.ipynb` in Jupyter Notebook to see the code and interactive plots (e.g., Cell 8’s 3D scatter plot).
- View PNG files (`histograms.png`, `boxplots_numerical.png`, etc.) in any image viewer.
- Open `3d_scatter.html` in a web browser (e.g., Chrome) to interact with the 3D scatter plot.
- Read `eda_inferences.txt` in a text editor for feature-level insights.
