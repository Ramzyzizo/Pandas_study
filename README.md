##essentials
__import pandas as pd___

pd.DataFrame(dataset or Dictionary) => create dataframe as table

pd.Series(dictionary) => create series as table

[] => series
[[]] => DataFrame 

pd.loc[index as 3] ##### row number 3

data=pd.read_csv('filename') => read csv file
pd.read_json('name.json') =>  read json file

print(data) => show first and last rows
print(data.to_string) => show all data

print(pd.options.display.max_rows) => what max number of rows to print

print(data.head(x)) =>  return x rows from top + header  =>   by default 5 rows
print(data.tail(x)) =>  return x rows from bottom + header  =>  by default 5 rows

print(data.info())  =>  return information who null and types of data

dt.sort_values('column',ascending=False)  =>  sorting data descending

############ cleaning data

newdata=data.dropna()  =>  remove any rows have null in a copy data
newdata=data.dropna(inplace=True)  =>  remopve any rows have null in origin data
de.dropna(subset=['column'],inplace=True)   =>  remove nun row in column
df.dropm(index,inplace=True)   =>  delete row by index

newdata=data.fillna(x,inplace=True)  =>  replace any null with x

data["column"].fillna(x)  =>  replace any null in column with x
#mean & median & mode
m=df["column"].mean()  =>  calc mean "average" of column 
m=df["column"].median()  =>  calc median "in middle" of column 
m=df["column"].mode()[0]  =>  calc mode "repeated value" of column 

########### editing data
df['column']=pd.to_datetime(df['column'])   =>  convert column to date type

df.loc[index,'column']=x   =>  set cel in column =x

df.duplicated()   =>  if duplicated => True else => False beside index of row
df.drop_duplicates()   =>  remove duplicated rows

df.replace(x,y,inplace=True)   =>  replace x with y in all data

########## pandas_plotting
import matplotlib.pyplot as plt

df.plot()   =>  plot data
plt.show()   =>   show graph in lines

df.plot(kind='scatter',x="column",y="column")   =>   scatter graph for column x and y
df["column"].plot(king='hist')   =>  histogram graph for column 

########## data_correlation

df.corr()   =>  table of correlations bertween columns  from 1 to -1 , best is 1:0.6 or -1:-0.6
