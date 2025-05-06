# Case_Study_5
# Read the Excel file
file_path = "students_data.xlsx"  # Replace with the actual file name
df = pd.read_excel(file_path)

# Calculate percentage
df['Percentage'] = (df['Marks'] / 15) * 100

# Categorize students
greater_75 = df[df['Percentage'] > 75]
between_60_75 = df[(df['Percentage'] >= 60) & (df['Percentage'] <= 75)]
less_60 = df[df['Percentage'] < 60]

# Print categorized students
print("\nStudents with > 75% marks:")
print(greater_75)

print("\nStudents with 60% to 75% marks:")
print(between_60_75)

print("\nStudents with < 60% marks:")
print(less_60)

# Plot Histogram
plt.figure(figsize=(7, 5))
plt.hist(df['Percentage'], bins=range(0, 101, 5), edgecolor='black', color='blue')
plt.xlabel('Percentage')
plt.ylabel('Number of Students')
plt.title('Histogram Plot')
plt.show()

# Plot Scatter Plot
plt.figure(figsize=(7, 5))
plt.scatter(df.index, df['Percentage'], color='blue')
plt.xlabel('Students')
plt.ylabel('Percentage')
plt.title('Scatter Plot')
plt.show()
