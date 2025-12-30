# Linear Regression without using libraries

# Step 1: Dataset
# X = input feature (e.g., area)
# Y = output (e.g., house price)
X = [1200, 1500, 1800, 2000, 2300]
Y = [3500000, 4500000, 5500000, 6200000, 7000000]

n = len(X)

# Step 2: Calculate mean of X and Y
mean_x = sum(X) / n
mean_y = sum(Y) / n

# Step 3: Calculate slope (m)
numerator = 0
denominator = 0

for i in range(n):
    numerator += (X[i] - mean_x) * (Y[i] - mean_y)
    denominator += (X[i] - mean_x) ** 2

m = numerator / denominator

# Step 4: Calculate intercept (c)
c = mean_y - m * mean_x

print("Linear Regression Equation:")
print(f"Y = {m:.2f}X + {c:.2f}")

# Step 5: Predict values
predicted_Y = []
for x in X:
    predicted_Y.append(m * x + c)

print("\nPredicted Values:")
for i in range(n):
    print(f"Actual: {Y[i]}  Predicted: {int(predicted_Y[i])}")

# Step 6: Performance Evaluation (Mean Squared Error)
mse = 0
for i in range(n):
    mse += (Y[i] - predicted_Y[i]) ** 2

mse = mse / n

print("\nModel Performance:")
print("Mean Squared Error (MSE):", int(mse))
