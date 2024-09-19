# Experiment 4 - Data Wrangling and Visualization

## Problem Overview

**ECE BOARD EXAM PROBLEM**: Using data wrangling and data visualization techniques with storytelling, analyze the dataset and present various (i) data frames; and (ii) visuals using the dataset provided.

### P1: Creating Data Frames

You are tasked with creating specific data frames by manipulating the dataset provided in **board2.xlsx**.

### Data Frame Formats:
1. **Vis**: 
   - Columns: ["Name", "Gender", "Track", "Math <70"]
   - Filter: Hometown is constant as Visayas.

2. **Instru**:
   - Columns: ["Name", "GEAS", "Electronics >70"]
   - Filter: Track is constant as Instrumentation, and Hometown is constant as Luzon.

3. **Mindy**:
   - Columns: ["Name", "Track", "Electronics", "Average >=55"]
   - Filter: Hometown is constant as Mindanao, and Gender is Female.

### P2: Data Visualization

Using the same data frames from P1, create a visualization to analyze how different features contribute to the average grade. Answer the question: Does the chosen track in college, gender, or hometown contribute to a higher average score?

## Setup Instructions

To complete this task, you will need the following:
1. **Anaconda Navigator**: With **Jupyter Notebook** installed for coding.
2. **board2.xlsx**: The Excel file containing the dataset.

### Brief Process for P1

1. **Import Libraries**:
   - Start by importing the required libraries:
     ```python
     import pandas as pd
     ```

2. **Load the Data**:
   - Read the Excel file to create the initial data frame:
     ```python
     data = pd.read_excel('board2.xlsx')
     ```

3. **Create the `Vis` DataFrame**:
   - Filter the data to include rows where Hometown is Visayas and Math scores are less than 70:
     ```python
     vis = data.loc[(data['Hometown'] == 'Visayas') & (data['Math'] < 70), ['Name', 'Gender', 'Track', 'Math']]
     ```

4. **Create the `Instru` DataFrame**:
   - Filter the data for Instrumentation track, Luzon as hometown, and Electronics scores greater than 70:
     ```python
     instru = data.loc[(data['Track'] == 'Instrumentation') & (data['Hometown'] == 'Luzon') & (data['Electronics'] > 70), ['Name', 'GEAS', 'Electronics']]
     ```

5. **Create the `Mindy` DataFrame**:
   - Filter the data for Mindanao as hometown, Female gender, and Average scores greater than or equal to 55:
     ```python
     mindy = data.loc[(data['Hometown'] == 'Mindanao') & (data['Gender'] == 'Female') & (data['Average'] >= 55), ['Name', 'Track', 'Electronics', 'Average']]
     ```

### Brief Process for P2

1. **Prepare Data for Visualization**:
   - For analyzing how different features contribute to the average grade, combine or transform the data as needed.
   
2. **Visualize the Data**:
   - Import **Matplotlib** and **Seaborn** for data visualization:
     ```python
     import matplotlib.pyplot as plt
     import seaborn as sns
     ```

   - Create bar plots, scatter plots, or other visuals to analyze features like track, gender, and hometown against average grades:
     ```python
     plt.figure(figsize=(10, 4))
     sns.barplot(x='Track', y='Average', data=data, hue='Gender')
     plt.title('Contribution of Track and Gender to Average Score')
     plt.show()
     ```

3. **Interpretation**:
   - Based on the visualizations, describe how each feature (Track, Gender, Hometown) affects the average grade.

## Conclusion

This experiment guides you through the process of wrangling data and visualizing it to uncover insights regarding the ECE board exam performance based on features such as Track, Gender, and Hometown. Through the creation of the specified data frames and visuals, you will analyze the contribution of each feature to the average grade.

---

### Author:
Yule Andre R. Osea

### Date per commit changes
Add the date of creation.
