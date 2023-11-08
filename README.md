import pandas as pd
import plotly.express as px
import plotly.graph_objects as go

data = pd.read_csv("ecommerce_customer_data.csv")
print(data.head())
User_ID  Gender  Age   Location Device_Type  Product_Browsing_Time  \
0        1  Female   23  Ahmedabad      Mobile                     60   
1        2    Male   25    Kolkata      Tablet                     30   
2        3    Male   32  Bangalore     Desktop                     37   
3        4    Male   35      Delhi      Mobile                      7   
4        5    Male   27  Bangalore      Tablet                     35   

   Total_Pages_Viewed  Items_Added_to_Cart  Total_Purchases  
0                  30                    1                0  
1                  38                    9                4  
2                  13                    5                0  
3                  20                   10                3  
4                  20    # Summary statistics for numeric columns
numeric_summary = data.describe()
print(numeric_summary)                8                2Customer Behaviour Analysis: Distribution of Age
Now, let’s have a look at the gender distribution:

1
# Bar chart for 'Gender'
2
gender_counts = data['Gender'].value_counts().reset_index()
3
gender_counts.columns = ['Gender', 'Count']
4
fig = px.bar(gender_counts, x='Gender', 
5
             y='Count', 
6
             title='Gender Distribution')
7
fig.show()
Gender Distribution
