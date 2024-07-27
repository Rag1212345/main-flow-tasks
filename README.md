import pandas as pd

# Read CSV file into DataFrame
df = pd.read_csv('/content/tested.csv')

# Display the first few rows of the DataFrame
print("Original DataFrame:")
print(df.head())

# Handling missing values
df_filled = df.fillna(0)
print("\nDataFrame with Missing Values Filled:")
print(df_filled.head())

# Removing duplicates
df_no_duplicates = df.drop_duplicates()
print("\nDataFrame without Duplicates:")
print(df_no_duplicates.head())

# Filtering data (example: passengers older than 30)
filtered_df = df[df['Age'] > 30]
print("\nFiltered DataFrame (Age > 30):")
print(filtered_df.head())

# Sorting data (example: by Age)
sorted_df = df.sort_values(by='Age')
print("\nSorted DataFrame by Age:")
print(sorted_df.head())

# Grouping data (example: mean Fare by Pclass)
grouped_df = df.groupby('Pclass')['Fare'].mean()
print("\nGrouped DataFrame by Pclass (mean Fare):")
print(grouped_df.head())
