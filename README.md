# Load necessary libraries
library(ggplot2)

# Create the dataset
data <- data.frame(
  age = c("12", "13", "14", "15", "16", "17", "18", "19", "20", "21", "22-23", "24-25", "26-29", "30-34", "35-49", "50-64", "65+"),
  n = c(2798, 2757, 2792, 2956, 3058, 3038, 2469, 2223, 2271, 2354, 4707, 4591, 2628, 2864, 7391, 3923, 2448),
  alcohol_use = c(3.9, 8.5, 18.1, 29.2, 40.1, 49.3, 58.7, 64.6, 69.7, 83.2, 84.2, 83.1, 80.7, 77.5, 75.0, 67.2, 49.3),
  marijuana_use = c(1.1, 3.4, 8.7, 14.5, 22.5, 28.0, 33.7, 33.4, 34.0, 33.0, 28.4, 24.9, 20.8, 16.4, 10.4, 7.3, 1.2),
  cocaine_use = c(0.1, 0.1, 0.1, 0.5, 1.0, 2.0, 3.2, 4.1, 4.9, 4.8, 4.5, 4.0, 3.2, 2.1, 1.5, 0.9, 0.0)
)

# Scatter plot of age vs. alcohol use
ggplot(data, aes(x = age, y = alcohol_use)) +
  geom_point() +
  geom_line() +
  labs(title = "Alcohol Use by Age", x = "Age", y = "Alcohol Use (%)")

# Bar chart of marijuana use by age
ggplot(data, aes(x = age, y = marijuana_use)) +
  geom_bar(stat = "identity") +
  labs(title = "Marijuana Use by Age", x = "Age", y = "Marijuana Use (%)")

# Histogram of cocaine use
ggplot(data, aes(x = cocaine_use)) +
  geom_histogram(binwidth = 0.5, fill = "blue", color = "black") +
  labs(title = "Histogram of Cocaine Use", x = "Cocaine Use (%)", y = "Frequency")
