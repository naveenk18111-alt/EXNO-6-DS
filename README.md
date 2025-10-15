# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
 ```
import seaborn as sns
import matplotlib.pyplot as plt

df=sns.load_dataset("tips")
df
```
<img width="868" height="833" alt="image" src="https://github.com/user-attachments/assets/092be2d4-2516-4bf8-a0ba-e8edb941fcf5" />



```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle="solid",legend="auto",palette="Set1")
```
<img width="1128" height="908" alt="image" src="https://github.com/user-attachments/assets/a88e4e42-3433-44d7-ae9a-a1c8dd336e77" />



```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x, y=y1)
sns.lineplot(x=x, y=y2)
sns.lineplot(x=x, y=y3)
plt.title("Multi-Line Plot")
plt.xlabel('X Label')
plt.ylabel('Y Label')
```
<img width="1111" height="959" alt="image" src="https://github.com/user-attachments/assets/106153d3-d3bb-45b5-923d-8ca8061e0ab4" />




```
tips = sns.load_dataset("tips")
avg_total_bill = tips.groupby("day")["total_bill"].mean()
avg_tip=tips.groupby("day")["tip"].mean()
plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill")
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="tip")
plt.xlabel("Day of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Day")
plt.legend()
plt.show()
```
<img width="1394" height="1258" alt="image" src="https://github.com/user-attachments/assets/1bb21e2a-03ea-42ec-beb0-a41e68391e0f" />



```
avg_total_bill=tips.groupby("time")["total_bill"].mean()
avg_tip=tips.groupby("time")["tip"].mean()
p1=plt.bar(avg_total_bill.index,avg_total_bill,label="Total Bill",width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label="tip",width=0.4)
plt.xlabel("Time of the week")
plt.ylabel("Amount")
plt.title("Average Total Bill and Tip by Time of the Day")
plt.legend()
plt.show()
```
<img width="1123" height="1049" alt="image" src="https://github.com/user-attachments/assets/9fa145a6-ff5b-4e83-88c6-1fb96be2dceb" />




```
import seaborn as sns
df=sns.load_dataset("tips")
sns.barplot(x="day",y="total_bill",hue="sex",data=df,palette='Set3')
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Total Bill by Day and Gender")
plt.show()
```
<img width="1139" height="951" alt="image" src="https://github.com/user-attachments/assets/18d3c6b6-8951-4bf0-97f5-728d390125da" />



```
import seaborn as sns
df=sns.load_dataset("tips")
sns.scatterplot(x="total_bill",y="tip",hue="sex",data=df,palette='Set1')
plt.xlabel("Total Bill")
plt.ylabel("Tip")
plt.title("Scatter Plot of Total Bill vs Tip Amount")
plt.show()
```
<img width="1139" height="930" alt="image" src="https://github.com/user-attachments/assets/068e5635-b5d7-4e18-9b51-83e1542d5511" />




```
sns.histplot(data=df,x="total_bill",hue="smoker",kde=True,palette="Set1")
plt.xlabel("Total Bill")
plt.ylabel("Frequency")
plt.title("Distribution of Total Bill by Gender")
plt.show()
```
<img width="1121" height="922" alt="image" src="https://github.com/user-attachments/assets/b4c802d3-e628-4779-a6da-e105eb7708a4" />



```
import seaborn as sns
import pandas as pd
df=sns.load_dataset('tips')
sns.boxplot(x='day',y='total_bill',hue='sex',data=df,palette='Set2')
```
<img width="1137" height="899" alt="image" src="https://github.com/user-attachments/assets/284be5e9-8fbe-4386-b3d7-ba4711596893" />




```
sns.boxplot(x="day",y="total_bill",hue="smoker",data=df,linewidth=2,width=0.6,fliersize=7,flierprops={"marker":"o","markerfacecolor":"grey"},boxprops={"facecolor":"red","edgecolor":"black"},whiskerprops={"color":"darkblue","linestyle":"--","linewidth":2},palette='Set1')
```
<img width="1124" height="909" alt="image" src="https://github.com/user-attachments/assets/118843f1-6038-4fea-82c9-a3bea876f5e2" />




```
sns.violinplot(x="day",y="total_bill",hue="smoker",data=tips,linewidth=2,width=0.6,palette='Set1',inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
<img width="1144" height="975" alt="image" src="https://github.com/user-attachments/assets/e5195b35-c61d-4461-b0a4-e8f825a78253" />



```
import seaborn as sns
sns.set(style="whitegrid")
tip = sns.load_dataset('tips')
sns.violinplot(x='day',y='tip',data=tip,palette="Set2")
```
<img width="1141" height="1089" alt="image" src="https://github.com/user-attachments/assets/03b16358-1951-46dd-80a4-0cb6138c671d" />



```
import seaborn as sns
sns.set(style='whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"],palette="Set1")
```
<img width="1062" height="1123" alt="image" src="https://github.com/user-attachments/assets/77b50a7b-2b25-4708-bae2-7fe8864a5050" />




```
import seaborn as sns
sns.set(style="whitegrid")
tips = sns.load_dataset('tips')
sns.violinplot(x="tip",y="day",data=tip,palette="rainbow")
```
<img width="1179" height="1094" alt="image" src="https://github.com/user-attachments/assets/e3176f60-e129-4409-b09a-4e9837dc8800" />




```
sns.kdeplot(data=tips,x='total_bill',hue='time', linewidth=3,palette='Set2',alpha=0.8)
```
<img width="1205" height="928" alt="image" src="https://github.com/user-attachments/assets/712fc2c0-4790-4aa5-996e-658e48842525" />





```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='stack', linewidth=3,palette='Set3',alpha=0.8)
```
<img width="1183" height="936" alt="image" src="https://github.com/user-attachments/assets/95451881-a583-45fd-808c-01c2bd797483" />



```
sns.kdeplot(data=tips,x='total_bill',hue='time', multiple='fill',linewidth=3,palette='Set1',alpha=0.8)
```
<img width="1164" height="948" alt="image" src="https://github.com/user-attachments/assets/12b2c2c8-253d-47f6-808b-358846f7c9ec" />



```
import seaborn as sns
tip = sns.load_dataset('tips')
num=tip.select_dtypes(include=['float64','int64']).columns
corr = tip[num].corr()
sns.heatmap(corr,annot=True,cmap="YlGnBu")
```
<img width="1045" height="875" alt="image" src="https://github.com/user-attachments/assets/f92ca090-cba1-42b4-9433-3b59e3f8e679" />



```
import seaborn as sns
import pandas as pd
tip = sns.load_dataset('tips')
num=tip.select_dtypes(include=['float64','int64']).columns
corr = tip[num].corr()
sns.heatmap(corr, cmap="YlGnBu")
```
<img width="1035" height="888" alt="image" src="https://github.com/user-attachments/assets/59822280-b055-4a87-ba6e-7e187c720156" />


# Result:
Thus the data visualiztion using seaborn library program was successfully executed.

