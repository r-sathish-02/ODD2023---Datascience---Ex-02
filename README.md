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
![dsex2](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/9de4e4dc-7621-4814-9a7c-0d6ab02592c1)

```
sns.boxplot(data=af)
```
![dsex2-2](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/dba8939d-fca8-41d6-a889-d9ead4ed807e)

```
sns.scatterplot(data=af)
```
![dsex2-3](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/effab3ce-bb80-4382-bdda-e75ebdae84fe)

```
q1=af.quantile(0.25)
q2=af.quantile(0.5)
q3=af.quantile(0.75)
iqr=q3-q1
```
```
low=q1-1.5*iqr
low
```
![dsex2-4](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/3590f2f1-b170-4b7e-8ef7-6d53514e4cf1)

```
high=q1+1.5*iqr
high
```
![dsex2-5](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/233193f0-dc9f-4e96-956e-3741407a7ad1)

```
aq=af[((af>=low)&(af<=high))]
aq.dropna()
```
![dsex2-6](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/75f11fc4-f4e2-41ff-b378-ae686570d195)

```
sns.boxplot(data=af)
```
![dsex2-7](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/306afc32-4873-4f76-95a9-d10655504295)

```
af=af[((af>=low)&(af<=high))]
af.dropna()
```
![dsex2-8](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/5feea074-1075-49b3-91b8-7ba0d911db30)

```
sns.boxplot(data=af)
```
![dsex2-9](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/4c028917-fbfe-4e1e-a86a-abf532f99e7b)

```
sns.scatterplot(data=af)
```
![dsex2-10](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/5994cf20-8646-4542-8f46-f8f141e136c8)

```
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
data = {'weight':[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,69,202,72,75,78,81,84,232,87,90,93,96,99,258]}
df=pd.DataFrame(data)
df
```
![dsex2-11](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/a5d32596-f371-4605-bf58-f187cf8dad19)

```
sns.boxplot(data=df)
```
![dsex2-12](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/68c4d57c-4a47-4cf5-ac9b-618025c70b8a)

```
z=np.abs(stats.zscore(df))
print(df[z['weight']>3])
```
![dsex2-13](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/ce3c06fd-dc9d-4641-8cb6-2d2db20847f2)

```
val=[12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,69,202,72,75,78,81,84,232,87,90,93,96,99,258]
out=[]
def d_o(val):
  ts=3
  m=np.mean(val)
  sd=np.std(val)
  for i in val:
    z=(i-m)/sd
    if np.abs(z)>ts:
      out.append(i)
  return out
op=d_o(val)
op
```
![dsex2-14](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/d26d5676-1c50-4912-bc53-39981ec130aa)

```
import pandas as pd
import numpy as np
import seaborn as sns
from scipy import stats
id=pd.read_csv("iris.csv")
id.head()
```
![dsex2-15](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/2ffda100-d3a3-4612-9016-228670add6d6)

```
sns.boxplot(x='sepal_width',data=id)
```
![dsex2-16](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/7c30d5d0-37e3-412d-8fd8-c3ed14f3f54b)

```
c1=id.sepal_width.quantile(0.25)
c3=id.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```
![dsex2-17](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/f529c8dc-35b2-49cb-bb48-0ebbcb8634d3)

```
rid=id[((id.sepal_width<(c1-1.5*iq))|(id.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```
![dsex2-18](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/2ee003cf-6115-4f80-b767-abd60e3dd158)

```
delid=id[~((id.sepal_width<(c1-1.5*iq))|(id.sepal_width>(c3+1.5*iq)))]
delid
```
![dsex2-19](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/02b14778-330f-4e88-b51c-c798ff113757)

```
sns.boxplot(x='sepal_width',data=delid)
```
![dsex2-20](https://github.com/r-sathish-02/ODD2023---Datascience---Ex-02/assets/118787261/4085fcb6-1839-4532-b680-dee3b3d42769)

# RESULT
Thus the outliers are detected and removed in the given file and the final data set is saved into the file.
