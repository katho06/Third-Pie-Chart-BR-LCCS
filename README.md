# Third-Pie-Chart-BR-LCCS
# EXAM NUMBER - 105626
import pandas as pd
import matplotlib.pyplot as plt

# Read CSV file into a pandas DataFrame
file_path = 'projectdata1.csv'
df = pd.read_csv(file_path)

# Calculate the total count of 'happy' and 'sad' occurrences
happy_count = df['sad'].sum()
sad_count = df['happy'].sum()
total_count = len(df)

# Calculate the percentage of happy and sad occurrences
happy_percentage = (happy_count / total_count) * 100
sad_percentage = (sad_count / total_count) * 100

#BR3 This pie chart predicts emotion form results of microbit data of students who study below national average
if happy_count > sad_count:
    print("Students who study below the national average usually tend to be less happy than those who study below average")
else:
    print("no difference between happiness of students who study above or below")

# Create a pie chart
labels = ['Happy', 'Sad']
sizes = [happy_percentage, sad_percentage]
colors = ['lightgreen', 'lightcoral']
explode = (0.1, 0)  # explode the 'Happy' slice for emphasis

plt.pie(sizes, explode=explode, labels=labels, colors=colors, autopct='%1.1f%%', shadow=True, startangle=140)
plt.axis('equal')  # Equal aspect ratio ensures that the pie chart is circular.

# Display the pie chart
plt.title('Mood of Students who study less than the national average')
plt.show()


