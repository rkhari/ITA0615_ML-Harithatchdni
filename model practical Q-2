# Step 1: Define the dataset
dataset = [
    ['Sunny', 'Warm', 'Normal', 'Strong', 'Warm', 'Same', 'Yes'],
    ['Sunny', 'Warm', 'High', 'Strong', 'Warm', 'Same', 'Yes'],
    ['Rainy', 'Cold', 'High', 'Strong', 'Warm', 'Change', 'No'],
    ['Sunny', 'Warm', 'High', 'Strong', 'Cool', 'Change', 'Yes']
]

# Step 2: Extract features and target
features = [row[:-1] for row in dataset]
target = [row[-1] for row in dataset]

# Step 3: Initialize most specific hypothesis
hypothesis = ['0'] * len(features[0])

# Step 4: Implement Find-S Algorithm
for i in range(len(features)):
    if target[i] == 'Yes':  # Only consider positive examples
        for j in range(len(hypothesis)):
            if hypothesis[j] == '0':
                hypothesis[j] = features[i][j]  # First positive example
            elif hypothesis[j] != features[i][j]:
                hypothesis[j] = '?'  # Conflict, generalize

# Step 5: Print the result
print("Most Specific Hypothesis:")
print(hypothesis)
