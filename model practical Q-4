# EM Algorithm for 1D Gaussian Mixture Model (Pure Python)

import math

# Step 1: Dataset
data = [1.2, 1.8, 2.5, 5.5, 6.1, 6.8]

# Step 2: Initial parameters
mean1, mean2 = 2.0, 6.0
var1, var2 = 1.0, 1.0
pi1, pi2 = 0.5, 0.5

# Gaussian probability function
def gaussian(x, mean, var):
    return (1 / math.sqrt(2 * math.pi * var)) * math.exp(-((x - mean) ** 2) / (2 * var))

# Step 3: EM iterations
iterations = 5

for step in range(iterations):
    print("\nIteration", step + 1)

    # E-Step: Responsibilities
    gamma1 = []
    gamma2 = []

    for x in data:
        p1 = pi1 * gaussian(x, mean1, var1)
        p2 = pi2 * gaussian(x, mean2, var2)
        total = p1 + p2

        gamma1.append(p1 / total)
        gamma2.append(p2 / total)

    # M-Step: Update parameters
    N1 = sum(gamma1)
    N2 = sum(gamma2)

    mean1 = sum(gamma1[i] * data[i] for i in range(len(data))) / N1
    mean2 = sum(gamma2[i] * data[i] for i in range(len(data))) / N2

    var1 = sum(gamma1[i] * (data[i] - mean1) ** 2 for i in range(len(data))) / N1
    var2 = sum(gamma2[i] * (data[i] - mean2) ** 2 for i in range(len(data))) / N2

    pi1 = N1 / len(data)
    pi2 = N2 / len(data)

    # Print parameters
    print("Mean1:", round(mean1, 2), "Variance1:", round(var1, 2), "Pi1:", round(pi1, 2))
    print("Mean2:", round(mean2, 2), "Variance2:", round(var2, 2), "Pi2:", round(pi2, 2))
