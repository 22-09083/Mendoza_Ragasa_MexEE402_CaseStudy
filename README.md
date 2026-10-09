# Mendoza_Ragasa_MexEE402_CaseStudy
# MexEE 402: Data Preprocessing Case Study

MexEE Elective 2: Data Science and Machine Learning
Batangas State University, Alangilan Campus
1st Semester, AY 2026-2027

## Members

| Name | Student Number | Section |
|---|---|---|
| Mendoza, Jose Roart B. | 22-09083 |MEXE-4103|
| Ragasa, Crist Gerrecho C. | 22-03893 | MEXE-4103 |

## Notebook links

| Chapter | Mendoza, Jose Roart B. | Ragasa, Crist Gerrecho C. |
|---|---|---|
| Ch1_2_3 |  | [Ch1_2_3](https://colab.research.google.com/drive/1h5qRqP2yVq7q_DGqXVYgt1aJmOTUTczf?usp=sharing) |
| Ch4 |  | [Ch4](https://colab.research.google.com/drive/1QSX6iYJk8a7quBz4MGfgpx-kLPDpae0D?usp=sharing) |
| Ch5 |  | [Ch5](https://colab.research.google.com/drive/14vB2TWBp3Zk61nS5o-yRDiqW-qzl-ODo?usp=sharing) |
| Ch6 |  | [Ch6](https://colab.research.google.com/drive/1blHDR_yFSLyD2S_Hn1qL6K0yiiPAuLEw?usp=sharing) |
| Ch7 |  | [Ch7](https://colab.research.google.com/drive/1B6-g_BiS0bvyHn5hucWI73BnBePJUIJ3?usp=sharing) |
| Ch8 |  | [Ch8](https://colab.research.google.com/drive/1cSWifZgEdwL914489O6Z5CmYB6iP7R3U?usp=sharing) |
| Ch9 |  | [Ch9](https://colab.research.google.com/drive/1Jhnwlj-WBdsSEHvH6Mx3joLiFlQmb2QV?usp=sharing) |

## What we learned

## ⬤ Ch1_2_3
We understood that raw datasets are inherently messy, miss values, and contain irrelevant noise, making preprocessing an essential first step before feeding data into a machine learning model. Using initial inspection methods like dtypes, head(), info(), and describe() gives a clear overview of the data's structural integrity. What surprised us most was how much summary statistics can be distorted by extreme outliers (like games with global sales over 40 million), showing how sensitive measures like mean and standard deviation are to uncleaned data.

## ⬤ Ch4
We learned how feature engineering transforms raw attributes into more informative variables using binning, interaction terms, and non-linear polynomial features. It also made clear the distinct roles of One-Hot Encoding for nominal variables and Ordinal Encoding for ranked variables. What surprised us was that using Ordinal Encoding on nominal categories without natural ordering (like weather types) accidentally forces an artificial mathematical hierarchy onto a model, leading it to misinterpret neutral categories as magnitudes.

## ⬤ Ch5
We understood that machine learning algorithms relying on distance calculations or gradient updates get severely biased when features exist on vastly different numerical scales. Rescaling features using StandardScaler (centering at mean=0, std=1) or MinMaxScaler (scaling within 0 to 1) levels the playing field so larger numbers don't dominate model behavior. What surprised us was learning that not all algorithms require scaling—tree-based models (like Decision Trees or Random Forests) are completely unaffected by feature scale because they split nodes based on relative threshold cutoffs.

## ⬤ Ch6
We learned how to systematically identify anomalous data points using statistical dispersion methods like Z-scores ($\pm 3\sigma$) and the Interquartile Range (IQR) fences. Handling outliers isn't strictly about deleting rows; alternative approaches like Winsorizing (capping/flooring) or log transformations preserve useful information while mitigating extreme values. What surprised us was how sensitive the Z-score calculation itself is to extreme outliers, as a massive outlier inflates both the mean and standard deviation, sometimes masking its own Z-score relative to the standard threshold cutoff.

## ⬤ Ch7
We understood that having more features does not automatically create a better model, as redundant or irrelevant variables increase noise, slow down training, and cause overfitting. Comparing Filter methods (correlation thresholds), Wrapper methods (RFECV), and Embedded methods (Lasso L1 regularization) showed how feature subsets are selected differently depending on the technique. What surprised us was how each method selected a completely different set of features on the exact same dataset, proving that feature selection depends heavily on the model and evaluation criteria used.

## ⬤ Ch8
We learned that building a Scikit-Learn Pipeline paired with a ColumnTransformer creates an automated, sequential assembly line for preprocessing raw data. This setup ensures that cleaning, imputation, and scaling are applied consistently across both training and test datasets. What surprised us was how easy it is to accidentally introduce data leakage into a workflow when preprocessing operations are executed manually prior to splitting datasets.

## ⬤ Ch9
We understood how to apply all fundamental preprocessing concepts to a complex real-world dataset like Titanic, managing mixed numerical and categorical features within a single unified pipeline. Combining automated column transformations with exploratory visualization confirmed that preprocessing drastically improves missing value counts and exposes clean survival trends. What surprised us was seeing how strong demographic patterns were (such as passenger class and embarkation port), proving that simple feature engineering and proper missing-data imputation directly surface predictive power.

## Errors we found

Errors We Found
Deprecation Warning with Chained inplace=True Assignment (Chapter 3)

Notebook Error:
df['Year'].fillna(df['Year'].mean(), inplace=True)
df['Publisher'].fillna(df['Publisher'].mode()[0], inplace=True)
Issue: Triggered a FutureWarning because calling .fillna(..., inplace=True) on a single DataFrame column via chained indexing (df[col]) is deprecated in Pandas and will fail in Pandas 3.0+.

Corrected Version: Reassign the column directly without inplace=True:

Python
df['Year'] = df['Year'].fillna(df['Year'].mean())
df['Publisher'] = df['Publisher'].fillna(df['Publisher'].mode()[0])
R² Score Warning on Small CV Folds in RFECV (Chapter 7)

Notebook Error:
selector = RFECV(estimator, step=1, cv=5) applied to df_2 (which only contains 7 sample rows).
Issue: Splitting 7 samples across 5 cross-validation folds leaves folds with only 1 test sample, raising an UndefinedMetricWarning: R^2 score is not well-defined with less than two samples.

Corrected Version: Adjust the cross-validation splits to match small sample sizes, or use a smaller cv fold count:

Python
selector = RFECV(estimator, step=1, cv=2)
Missing Category Visual Mapping Bug in Discretization Plot (Chapter 9)

Notebook Error:
plt.hist(titanic_preprocessed[:,2], alpha=0.5, label='After discretization')
Issue: Column index 2 in titanic_preprocessed points to the One-Hot encoded Embarked_C binary column, not the discretized Age column. Passing index 2 plotted 0s and 1s rather than the discretized age categories.

Corrected Version: Plot the discretized Age categorical column directly from the underlying DataFrame:

Python
plt.hist(data['Age'].astype(str), alpha=0.5, label='After discretization')

## Note on AI tools

We utilized Gemini (Google AI) and ChatGPT (OpenAI) as interactive AI collaborators and study assistants for this activity. Specifically, we used these AI tools to:

Verify mathematical outputs and step-by-step code execution results across our notebooks.

Interpret warning tracebacks and identify Pandas deprecation warnings in the original code.

Brainstorm, format, and refine our written explanations, summary tables, and final report sections.

## References

McKinney, W. (2021). Python for Data Analysis, 3rd ed. O'Reilly Media.

VanderPlas, J. (2016). Python Data Science Handbook: Essential Tools for Working with Data. O'Reilly Media.

Scikit-Learn Developers. (2024). ColumnTransformer with Mixed Types. Scikit-Learn Documentation. https://scikit-learn.org/stable/auto_examples/compose/plot_column_transformer_mixed_types.html

Pandas Development Team. (2024). What's new in version 2.2.0: Copy-on-Write and Inplace Deprecations. Pandas Documentation. https://pandas.pydata.org/docs/whatsnew/v2.2.0.html
