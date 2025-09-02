# Exp.No:34  
## PREFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Define a set of valid operators: `*, -, +, %, /, **`.
3. Initialize an empty stack.
4. Traverse the prefix expression from **right to left**:
   - If the character is a **digit**, convert it to an integer and push it onto the stack.
   - If the character is an **operator**, pop two elements from the stack.
     - Apply the operator on the two popped operands.
     - Push the result back onto the stack.
   - If an invalid character is encountered, raise an error.
5. After traversal, the stack should contain only **one element**.
6. Return the **single element** as the evaluation result.
7. **End the program.**

---

### PROGRAM

```
OPERATORS = set(['*', '-', '+', '%', '/', '**'])

def evaluate(expression):
    stack = []
    for i in reversed(expression):
        if i not in OPERATORS:
            stack.append(i)
        else:
            a = stack.pop()
            b = stack.pop()
            if i == '+':
                res = int(a) + int(b)
            elif i == '*':
                res = int(a) * int(b)
            elif i == '-':
                res = int(a) - int(b)
            elif i == '/':
                res = int(a) // int(b)
            elif i == '%':
                res = int(a) % int(b)
            elif i == '**':
                res = int(a) ** int(b)
            stack.append(res)
    return stack[0]

test_expression = input()
print("Prefix Expression :", test_expression)
print("Evaluation result :", evaluate(test_expression))


```


### OUTPUT
<img width="818" height="198" alt="image" src="https://github.com/user-attachments/assets/ef01dd80-991b-41df-8ff1-d3a9f3043eaa" />




### RESULT:
Thus a Python program to evaluate a user-given Prefix expression using a stack has been executed successfully.
