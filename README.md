Postfix Evaluation (Basic Program)

def evaluate_postfix(exp):
    stack = []

    for ch in exp:
        if ch.isdigit():
            stack.append(int(ch))
        else:
            b = stack.pop()
            a = stack.pop()

            if ch == '+':
                stack.append(a + b)
            elif ch == '-':
                stack.append(a - b)
            elif ch == '*':
                stack.append(a * b)
            elif ch == '/':
                stack.append(a / b)

    return stack[0]

exp = "23*5+"
print("Postfix Expression:", exp)
print("Result:", evaluate_postfix(exp))

Output:
Postfix Expression: 23*5+
Result: 11
