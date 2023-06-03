# Ex-09-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df=sns.load_dataset("tips")
df

df.isnull().sum()

df.duplicated().sum()

df.dropna(how="all")

df.dropna(how="any")

cols=['size','tip','total_bill']
q1=df.quantile(0.75)
q3=df.quantile(0.25)
iqr=q3-q1
low=q1+1.5*iqr
high=q3-1.5*iqr
df2=df[(df[cols]>low)&(df[cols]<high)]
df2

sns.lineplot(x=df['day'],y=df['total_bill'])

sns.lineplot(x=df['day'],y=df['total_bill'],hue=df['sex'])


sns.barplot(x=df['size'],y=df['total_bill'])
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['sex'])
sns.barplot(data=df, x='day', y='tip')
average_bill_by_size = df.groupby('size')['total_bill'].mean()
max_average_bill = average_bill_by_size
max_average_bill

average_bill=df.loc[:,['size','total_bill']]
average_bill=df.groupby(by=['size']).mean().sort_values(by=['total_bill'])
sns.barplot(x=average_bill.index,y='total_bill',data=average_bill)
plt.show()

avg_total_bill = df.groupby('time')['total_bill'].sum()
avg_tip = df.groupby('time')['tip'].sum()

p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom = avg_total_bill, label='Tip', width=0.4)
plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
plt.show()

sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()

sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()

sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()
```

# OUPUT

![Screenshot (490)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/bfcf870e-cce6-4173-a31c-090a80e02304)


![Screenshot (491)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/cb391cd2-0710-40ec-9786-1c54b228a571)


![Screenshot (492)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/bf392891-830b-43b7-8e63-2c3d48d65c8e)


![Screenshot (493)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/835876a6-5532-487b-bfa0-c04b85890d3c)


![Screenshot (494)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/3967fedc-dffd-4f91-bddc-e24aaa7b20eb)


![Screenshot (495)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/dec2530a-55e3-41e7-a1a2-2863778d9786)


![Screenshot (496)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/0d9c11b2-a752-4ecc-93a8-442810acde2f)


![Screenshot (496)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/f2be5cf2-af20-4332-8663-99ad461d529d)


![Screenshot (498)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/efbdab6b-6ff1-4978-ac0d-d7a985ffd341)


![Screenshot (499)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/a60c2e81-8a14-40ca-b744-26b779258dd7)


![Screenshot (500)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/2635d5e8-9eee-4230-9e3f-9f68ff738c09)


![Screenshot (501)](https://github.com/VIJAYKUMAR22007124/Ex-08-Data-Visualization_1/assets/119657657/bd4b5d88-644b-420c-88fc-c6ac67170058)


# RESULT:

Performed Data Visualization on a complex dataset and saved the data to a file.
