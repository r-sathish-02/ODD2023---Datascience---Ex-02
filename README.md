# Ex02-Outlier
# AIM
You are given bhp.csv which contains property prices in the city of banglore, India. You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

# ALGORITHM
STEP 1:Read the given Data.

STEP 2:Get the information about the data.

STEP 3:Detect the Outliers using IQR method and Z score.

STEP 4:Remove the outliers:

STEP 5:Plot the datas using box plot.

# CODE and OUTPUT
```
NAME : SATHISH R
REG NO : 212222230138
```
```
import pandas as pd
import seaborn as sns
age = [1,3,28,27,25,92,30,39,40,50,26,24,29,94]
af=pd.DataFrame(age)
af
```
