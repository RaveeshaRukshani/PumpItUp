# PumpItUp
GitHub Page: [https://github.com/RaveeshaRukshani/PumpItUp](https://github.com/RaveeshaRukshani/PumpItUp).

## Explotary Data Analysis
- First download the train_values, train_labels and test_values data, merge train_labels to train_value   dataframe and try to understand the column meaning one by one.
- Variable Identification
  - Identify the type of the variables in the data.
  - View some basic statistical details like count, mean, std, min and max.
  - Check unique values, duplicate values, null values and missing values.
- Some column has large unique values. Then they were dropped it out. (id, amount_tsh, date_recorded, wpt_name, num_private, basin and etc.. )
- Some columns which has missing values, null values and unexpected values were replaced to unknown, mean and most common value. (funder, installer, population, puplic_meeting and etc…)
- Some columns which has same information different type. Then they were dropped and keep one of them by considering more unique values. (region and region_code, scheme_management, management and management_group )
- Some values in columns can be categorized using largest 20 values or some categorical patterns and make new column for categorical feature and dropped it. (new categoricall features - founder_grp, installer_grp, era)
- Some columns has lots of spelling mistakes and that create more unique values. So by considering those spelling mistakes create new categories. (installer)  

- Findings -
  - Most of them are functional and have imbalanced target dataset.
  - Higher population areas have more functional wells.
  - Can find how region affect to the functionality of water points. Can found Arusha region has 2294 functional water points.
  - Managements like company and other-school has more non-functional water points than functional water points.
  - Salty and unknown type water_quality has more non-functional water points than functional water points.
  - Most dry quantity water points are non-functional.

## Pre-processing and Feature Engineering approach
- Imputation – 
  - Missing values are replaced to mean value or most common value
- Discretization – 
  - Grouping values based on value patterns like construction year can be categorized to 60,70,80,.. like this.
  - Grouping values using largest 20 values and other values group as “Others”
- Categorical Encoding – 
  - labelEncoder is used to label the status_group column.
  - TargetEncoder is used to encode other categorical variables in train_dataset.
- Scaling – 
  - RobustScaler is used to scale the numerical variables.
- Creating Features –
  - Create new features by categorizing some columns like founder_grp by categorizing funder column, installer_grp by categorizing installer column, era by categorizing construction_year and etc.
- Convert Boolean values to int data type.
- ColumnTransformer is used to selectively prepare the columns of the dataset by scaling and encoding relative numerical column and categorical columns before fitting the model.

## Modeling approaches
- XGBoost
- Random Forest (best score get without oversampling)

## Post-Processing
- Feature Importance - 
  - According to the plot permit feature has more importance and latitude feature has less importance.



