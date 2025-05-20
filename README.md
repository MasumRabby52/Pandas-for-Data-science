# Pandas-for-Data-science

# importing a data set
~~~
import pandas as np
d=np.read_csv('Data.csv')
d
~~~
# Make Table from data
~~~
d=pd.DataFrame(Data)
~~~

# some function

~~~
d.info()
d.isnull()
d.isnull().sum()
d.describe()
d.describe().T
~~~
# For delet a row
   d.drop(index) </br>
   d.drop([index1,index2,index3])
~~~
d=d.drop(4)
d=d.drop([0,4,6])
~~~

# for delete a column
d=d.drop("name of a column",axis=1) </br>
d=d.drop(["column1","column2"],axis=1)
~~~
d=d.drop("Math Marks",axis=1)
d=d.drop(["Math Marks","English Marks"],axis=1)
~~~

#for delete duplicate value
~~~
d=d.drop_duplicates()
d
~~~

#for delet all null rows and reset index
~~~
d=d.dropna()
d.reset_index(drop=True)
d
~~~

# Replace a value in all row
~~~
d=d.fillna(130)
~~~

# Replace a value in a column

~~~
d=d.fillna({"Math Marks":130})
~~~

# Replace mean median mode in empty column

~~~

x=d["Math Marks"].mean()
d=d.fillna({"Math Marks":x})
d

x=d["Math Marks"].median()
d=d.fillna({"Math Marks":x})
d

x=d["Math Marks"].mode()[0]
d=d.fillna({"Math Marks":x})
d
~~~

# Convert Into a Correct Format
~~~
d['Date'] = pd.to_datetime(d['Date'], format='mixed')
d
~~~

# Delete rows where math Marks is higher than 90:

~~~
for x in d.index:
  if d.loc[x, "Math Marks"] > 90:
    d=d.drop(x)
d
~~~
# Replace rows where math marks is higher than 120 is 90
~~~
for x in d.index:
  if d.loc[x, "Math Marks"] > 90:
    d=d.fillna(90)
d
~~~

# To save Editing File
~~~
d.to_csv("Masum.csv")
~~~



