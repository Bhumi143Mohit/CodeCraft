# CodeCraft
Reverse a Stack You are given a stack of integers. Your task is to reverse the order of the elements in the stack using only stack operations (push & pop) & without using any additional data structures. Ex. stack = [1,2,3,4,5] reverse Stack[stack] print[stack].
Output should be [5,4,3,2,1].

 # Function to insert an element at the bottom of the stack
def insert_at_bottom(stack, element):
    if not stack:
        stack.append(element)
    else:
        # Pop all elements and insert the element at the bottom
        temp = stack.pop()
        insert_at_bottom(stack, element)
        # Push the popped element back
        stack.append(temp)

# Function to reverse the stack
def reverse_stack(stack):
    if stack:
        # Pop the top element
        temp = stack.pop()
        # Reverse the remaining stack
        reverse_stack(stack)
        # Insert the popped element at the bottom
        insert_at_bottom(stack, temp)

# Example usage:
stack = [1, 2, 3, 4, 5]
print("Original stack:", stack)

# Call the reverse function
reverse_stack(stack)

# Print the reversed stack
print("Reversed stack:", stack)


### Output:

Original stack: [1, 2, 3, 4, 5]
Reversed stack: [5, 4, 3, 2, 1]


