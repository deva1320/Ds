#include <stdio.h>
#include <ctype.h>
#define MAX 100

char stack[MAX];
int top = -1;

void push(char c) { stack[++top] = c; }
char pop() { return stack[top--]; }
int precedence(char c) {
    if (c == '^') return 3;
    if (c == '*' || c == '/') return 2;
    if (c == '+' || c == '-') return 1;
    return -1;
}

int main() {
    char exp[MAX], result[MAX];
    int i, k = 0;
    printf("Enter infix expression: ");
    scanf("%s", exp);

    for (i = 0; exp[i] != '\0'; i++) {
        if (isalnum(exp[i]))
            result[k++] = exp[i];
        else if (exp[i] == '(')
            push(exp[i]);
        else if (exp[i] == ')') {
            while (top != -1 && stack[top] != '(')
                result[k++] = pop();
            pop(); // remove '('
        }
        else {
            while (top != -1 && precedence(stack[top]) >= precedence(exp[i]))
                result[k++] = pop();
            push(exp[i]);
        }
    }
    while (top != -1) result[k++] = pop();
    result[k] = '\0';

    printf("Postfix Expression: %s\n", result);
    return 0;
}
