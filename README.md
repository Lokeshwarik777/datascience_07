# datascience_07

```python
def searchMatrix(matrix, target):
    if not matrix or not matrix[0]:
        return False

    rows = len(matrix)
    cols = len(matrix[0])

    # Binary search
    left, right = 0, rows * cols - 1
    while left <= right:
        mid = (left + right) // 2
        mid_element = matrix[mid // cols][mid % cols]
        if mid_element == target:
            return True
        elif mid_element < target:
            left = mid + 1
        else:
            right = mid - 1

    return False

# Function to get user input matrix
def get_user_matrix(rows, cols):
    matrix = []
    print("Enter the elements of the matrix:")
    for i in range(rows):
        row = list(map(int, input().split()))
        matrix.append(row)
    return matrix

# Get user input for matrix dimensions
rows = int(input("Enter the number of rows: "))
cols = int(input("Enter the number of columns: "))

# Get user input for the target value
target = int(input("Enter the target value: "))

# Get user input matrix
matrix = get_user_matrix(rows, cols)

# Call the function
result = searchMatrix(matrix, target)

# Print the result
print("Target value found:", result)
```