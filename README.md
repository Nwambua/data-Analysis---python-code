# data-Analysis---python-code
Accessing and manipulation files  
import pandas as pd
#import numpy as np

#Identify file location/directory 
import os
directory = os.getcwd()
directory

#get the file from directory
dfile = pd.read_csv('Myreport-2018.csv', encoding = "ISO-8859-1", engine='python')

# remove the null value records in the file 

F_dfile = dfile.dropna(how="any")

F_dfile.head(2)

#identify the headers used in the file
F_dfile.columns

#sort the data file
sorted_dfile = F_dfile.sort_values(by="S_Name")

#get specific columns 
select_file = sorted_dfile[['S_Name','RatioCount']]

#select the four records on file
select_file[0:3]

#count of selection
select_file.iloc[:3].count()

#sort the data according to prefered field
selct_file.sort_values(by='firstname', ascending=True )

#filter with apply function for specific data sets 
resolved = dfile.apply(lambda x: x[0])

#use axis to get row values/inputs in index three
resolved = dfile.apply(lambda x:x[3], axis=1 )

#Grouped by field name with records !>10000
No_unique = dfile[:10000].groupby('Field_Name')

#Display first few head
No_unique.head()

#multiple grouping with values !> 20000 get the first few rows

multiple_group = dfile[:20000].groupby(['field_name1','field_name2'])
multiple_group.first()

