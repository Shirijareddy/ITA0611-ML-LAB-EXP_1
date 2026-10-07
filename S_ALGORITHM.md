# FIND-S Algorithm

# Training data
training_data = [
    ['Sunny', 'Warm', 'Normal', 'Strong', 'Warm', 'Same', 'Yes'],
    ['Sunny', 'Warm', 'High', 'Strong', 'Warm', 'Same', 'Yes'],
    ['Rainy', 'Cold', 'High', 'Strong', 'Warm', 'Change', 'No'],
    ['Sunny', 'Warm', 'High', 'Strong', 'Cool', 'Change', 'Yes']
]

# Initialize hypothesis with the most specific values
hypothesis = ['0', '0', '0', '0', '0', '0']

# FIND-S algorithm
for row in training_data:
    if row[-1] == 'Yes':       # Consider only positive examples
        for i in range(len(hypothesis)):
            if hypothesis[i] == '0':
                hypothesis[i] = row[i]
            elif hypothesis[i] != row[i]:
                hypothesis[i] = '?'

# Display result
print("Most Specific Hypothesis:")
print(hypothesis)
