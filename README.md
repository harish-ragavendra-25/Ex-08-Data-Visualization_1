# Ex-08-Data-Visualization-

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
DEVELOPED BY: HARISH RAGAVENDRA S
RESISTER NO: 212222230045
```
```
import pandas as pd
import seaborn as sns
df=sns.load_dataset("tips")
df
```
```
df.isnull().sum()
```
```
import matplotlib.pyplot as plt
plt.figure(figsize=(7,7))
plt.title("Data with outliers")
df.boxplot()
plt.show()
```
```
cols=['size','tip','total_bill']
q1=df.quantile(0.75)
q3=df.quantile(0.25)
iqr=q3-q1
low=q1+1.5*iqr
high=q3-1.5*iqr
df2=df[(df[cols]>low)&(df[cols]<high)]
df2
```
```
df2=df2.drop(['sex','smoker','day','time'],axis=1)
df2
```
```
import seaborn as sns
import matplotlib.pyplot as plt
sns.barplot(x=df["day"],y=df["total_bill"],hue=df["day"])
plt.title("TOTAL BILL VS DAY")
plt.show()
```
```
sns.barplot(x=df["smoker"],y=df["tip"],hue=df["day"])
plt.title("What is the average tip amount given by smokers and non-smokers")
plt.show()
```
```
df["tip_percent"] = df["tip"] / df["total_bill"]
sns.scatterplot(x=df['size'],y=df['tip_percent'],data=df)
plt.title("Tip Percentage by Dining Party Size")
```
```
sns.boxplot(x=df['sex'], y=df['tip'],hue=df['sex'])
plt.title("Tips based on gender")
```
```
sns.scatterplot(x=df['day'],y=df['total_bill'],hue=df['day'])
plt.legend(loc="best")
plt.title("Total bill amount by day of the week")
```
```
sns.histplot(data=df, x="total_bill", hue="time", element="step", stat="density")
plt.title("Distribution of Total Bill Amounts by Time of Day")
```
```
sns.barplot(x=df['size'],y=df['total_bill'],hue=df['size'])
plt.title("Average Total Bill Amount by Dining Party Size")
plt.show()
```
```
sns.boxplot(x="day", y="tip", data=df)
plt.title("Tip Amount by Day of Week")
plt.show()
```
```
sns.violinplot(x="time", y="tip", data=df)
plt.title("Tip Amount by Time of Day")
plt.show()
```
```
sns.scatterplot(x="total_bill", y="tip", data=df)
plt.title("Correlation between Tip Amount and Total Bill Amount")
plt.show()
```
# OUPUT
![Screenshot 2023-05-30 212225](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/9456e33a-85f8-43c8-9d25-3928811beef3)
![Screenshot 2023-05-30 212235](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/01e2df5b-da53-4d7b-9012-63990dad818e)
![Screenshot 2023-05-30 212249](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/b52d94e3-4b09-42ff-ae28-310bdb365eb4)
![Screenshot 2023-05-30 212257](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/29756c91-36b5-4102-b831-ed92fb9b5013)
![Screenshot 2023-05-30 212305](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/666dce18-dfc8-4eb3-8234-86903358fe3b)
![Screenshot 2023-05-30 212318](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/7719a047-3e05-45cc-88d1-d80bf255811b)
![Screenshot 2023-05-30 212325](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/10c2ed6a-d128-4b89-b66b-b21e2b108059)
![Screenshot 2023-05-30 212341](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/cd4e1b24-d330-4172-b528-5de5a33be38e)
![Screenshot 2023-05-30 212356](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/123be028-7c81-460b-896f-497d4d1c800a)
![Screenshot 2023-05-30 212405](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/e11a2ad2-2492-4ec0-bfad-6c3dbd500421)
![Screenshot 2023-05-30 212417](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/47b61a6e-05bd-4d58-aa3a-21951fd11ae4)
![Screenshot 2023-05-30 212426](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/d9059ea4-9de1-4d2f-b017-e0b315d70baa)
![Screenshot 2023-05-30 212436](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/ae65f917-ba20-4de6-a780-816a2dab2368)
![Screenshot 2023-05-30 212444](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/bf22dd37-bccb-4e16-a3a8-49b2bc05d3c1)
![Screenshot 2023-05-30 212452](https://github.com/harish-ragavendra-25/Ex-08-Data-Visualization_1/assets/114852180/af9bd1a6-4fb1-47da-ae6e-d3eaf582df5b)
# RESULT:
Thus the experiment executed sucessfully.
