ECHO is on.

import matplotlib as mpl
import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd


# Data
x = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October']
weights = [322, 320, 310, 318, 290, 295, 305, 310, 300, 299]  # Weights
dose = [0, 0, 0, 0, 0.25, 0.25, 0, 0, 0.50, 0.50]  # Semaglutide Dose

# Create the plot
fig, ax1 = plt.subplots(figsize=(15, 10))

# Plot the weights
ax1.plot(x, weights, '--ro', linewidth=2, markeredgecolor='orchid', markerfacecolor='green', markeredgewidth=4)
ax1.set_xlabel("Month")
ax1.set_ylabel("Weight (lbs)", color='red')
ax1.tick_params('y', labelcolor='red')

# Create a second y-axis for the dose
ax2 = ax1.twinx()
ax2.plot(x, dose, 'b-', linewidth=2)  # Plot dose on the second y-axis
ax2.set_ylabel("Semaglutide Dose", color='blue')
ax2.tick_params('y', labelcolor='blue')

# Set title and grid
ax1.set_title("Nick's Weight and Semaglutide Dose 2024")
plt.grid(True)

ax1.legend(['Weight V. Dose'])

plt.show()