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
| Ch1_2_3 | [link]() | [Ch1_2_3](https://colab.research.google.com/drive/1h5qRqP2yVq7q_DGqXVYgt1aJmOTUTczf?usp=sharing) |
| Ch4 | [link]() | [Ch4](https://colab.research.google.com/drive/1QSX6iYJk8a7quBz4MGfgpx-kLPDpae0D?usp=sharing) |
| Ch5 | [link]() | [Ch5](https://colab.research.google.com/drive/14vB2TWBp3Zk61nS5o-yRDiqW-qzl-ODo?usp=sharing) |
| Ch6 | [link]() | [Ch6](https://colab.research.google.com/drive/1blHDR_yFSLyD2S_Hn1qL6K0yiiPAuLEw?usp=sharing) |
| Ch7 | [link]() | [Ch7](https://colab.research.google.com/drive/1B6-g_BiS0bvyHn5hucWI73BnBePJUIJ3?usp=sharing) |
| Ch8 | [link]() | [Ch8](https://colab.research.google.com/drive/1cSWifZgEdwL914489O6Z5CmYB6iP7R3U?usp=sharing) |
| Ch9 | [link]() | [Ch9](https://colab.research.google.com/drive/1Jhnwlj-WBdsSEHvH6Mx3joLiFlQmb2QV?usp=sharing) |

## What we learned

## Chapter 1, 2, and 3 
From Chapters 1–3, we learned that preparing data properly is an important step before using a machine-learning model. We also learned how to inspect and clean datasets, handle missing values, identify outliers, select useful features, and organize preprocessing steps using pipelines. These processes help make the data more consistent and reliable so the ML model can produce better results.
## Chapter 4
In Chapter 4, we learned that feature engineering involves creating or transforming features to make the data more useful for a machine-learning model. We learned how to create new features, group numerical values through binning, create interaction features, and convert categorical data using one-hot and ordinal encoding. These techniques can help the model identify useful patterns in the data.
## Chapter 5
Chapter 5 focuses on data scaling, which is used to put different features on a similar numerical scale before using them in a machine-learning model. We learned that StandardScaler changes the mean to 0 and standard deviation to 1, while MinMaxScaler changes values to a range of 0 to 1. The main purpose is to prevent features with larger numbers from having more influence on the model just because of their scale. We also learned that scaling is not always necessary and depends on the data and the machine-learning algorithm being used.
## Chapter 6
Chapter 6 focuses on identifying and handling outliers in a dataset. We learned that outliers are values that are significantly different from most of the other data and can affect the performance of a machine-learning model. The Z-score and IQR methods can be used to detect these unusual values. After finding an outlier, it can either be adjusted using capping or flooring, or removed if it is caused by an error or is not useful for the analysis.
## Chapter 7
Chapter 7 focuses on feature selection, which involves choosing the most useful features for a machine-learning model. We learned that selecting important features can make a model simpler, faster, and less likely to overfit. Different methods such as Filter, RFECV (Wrapper), and LassoCV (Embedded) can be used to determine which features are useful. This helps the model focus on the data that is most relevant to its predictions.
## Chapter 8
Chapter 8 focuses on using preprocessing pipelines to organize and automate data preparation. Similar to a conveyor belt, the data passes through each preprocessing step in the correct order before being given to the machine-learning model. We learned how imputation can fill missing values and scaling can standardize features. We also learned how ColumnTransformer can apply specific preprocessing steps to selected columns, making the overall workflow more organized and consistent.
## Chapter 9
Chapter 9 focuses on preparing numerical and categorical data before using it in a machine-learning model. We learned how to handle missing values differently depending on the type of feature, as well as how discretization can convert numerical values such as age into categories. We also used different plots to examine survival based on factors such as gender and passenger class. Overall, the chapter shows how proper preprocessing and visualization can help us better understand and prepare data for machine-learning analysis.

## Errors we found

List any mistake you found in the original notebooks, and the correct version.
There are real ones in there. Finding them earns points.

## Note on AI tools

Say whether you used an AI tool, and what for. This is not a penalty.
Hiding it is.

## References

McKinney, W. (2021). Python for Data Analysis, 3rd ed. O'Reilly.
VanderPlas, J. Python Data Science Handbook.
Any other page or article you used.
