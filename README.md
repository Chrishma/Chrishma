import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Create the dataset
data = {
    "Month": ["January", "February", "March", "April", "May"],
    "Traditional Dairy Sales ($)": [20000000, 20500000, 21000000, 21500000, 22000000],
    "Market Share (Traditional Dairy)": [50, 51, 52, 53, 54],
    "Plant-Based Competitor Sales ($)": [5000000, 5200000, 5300000, 5500000, 5700000],
    "Competitor Market Share (Plant-Based)": [20, 21, 22, 23, 24],
    "Production Cost per Unit (Traditional) ($)": [0.50, 0.50, 0.48, 0.48, 0.47],
    "Production Cost per Unit (Plant-Based) ($)": [0.65, 0.65, 0.63, 0.63, 0.62],
    "Consumer Awareness of Vinamilk Plant-Based Line (%)": [10, 12, 15, 18, 20]
}

# Convert data to DataFrame
df = pd.DataFrame(data)

# Statistical Analysis
stats_summary = df.describe()

# Mode
mode_values = df.mode().iloc[0]

# Median
median_values = df.median()

# Print Statistical Results
print("Summary Statistics:\n", stats_summary)
print("\nMode:\n", mode_values)
print("\nMedian:\n", median_values)

# Data Visualization

# Bar Graph: Traditional Dairy Sales vs. Plant-Based Competitor Sales
plt.figure(figsize=(10, 6))
sns.barplot(x="Month", y="Traditional Dairy Sales ($)", data=df, color='blue', label="Traditional Dairy")
sns.barplot(x="Month", y="Plant-Based Competitor Sales ($)", data=df, color='green', label="Plant-Based")
plt.title("Sales Comparison: Traditional Dairy vs. Plant-Based")
plt.ylabel("Sales ($)")
plt.legend()
plt.show()

# Bar Graph: Consumer Awareness of Vinamilk Plant-Based Line
plt.figure(figsize=(10, 6))
sns.barplot(x="Month", y="Consumer Awareness of Vinamilk Plant-Based Line (%)", data=df, palette="viridis")
plt.title("Consumer Awareness Growth of Vinamilk Plant-Based Line")
plt.ylabel("Consumer Awareness (%)")
plt.show()

