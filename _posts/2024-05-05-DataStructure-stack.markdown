---
layout: post
title:  "Data Structure: Stack"
date:   2024-05-05 09:00:00 +0900
categories: [Data Structure]
---

### Concept of Stack   
// 스택의 개념   
   
#### Definition of Stack   
// 스택의 정의   
   
// 객체와 그 객체가 저장되는 순서를 기억하는 방법에 관한 자료구조   
// - 가장 먼저 입력된 자료가 가장 나중에 출력되는 관계를 표현함   
// - 관계를 표현하기 위해서 연산이 필요하며, 객체에 대한 정의와 연산이 모여서 순서가 기억되는 스택의 추상 자료형이 완성됨   
- Data structure on how to remember objects and the order in which they are stored   
  - Expresses the relationship in which the first data entered is the last to be printed   
  - Operations are required to express the relationship, and the definition and operation of the object are combined to complete the abstract data type of the stack in which the order is remembered   
   
// 0개 이상의 원소를 갖는 유한 순서 리스트   
- A finite ordered list with zero or more elements   
   
// push (add) 와 pop (delete) 연산이 한 곳에서 발생되는 자료구조   
- Data structure where push (add) and pop (delete) operations occur in one place   
   
<br />
### Abstract data type of Stack   
// 스택의 추상 자료형   
   
// 스택 객체 : 0개 이상의 원소를 갖는 유한 순서 리스트   
- Stack object : A finite ordered list with zero or more elements   
   
#### CreateStack operation   
// CreateStack 연산   
   
// stack ∈ Stack, item ∈ element, maxStackSize ∈ positive integer 인 모든 stack, item, maxStackSize에 대하여 다음과 같은 연산이 정의된다   
- For all 'stack, item and maxStackSize' which is 'stack ∈ Stack, item ∈ element and maxStackSize ∈ positive integer', the following operation is defined   
   
```c
Stack CreateStack(maxStackSize) ::= 
    // 스택의 크기가 maxStackSize인 빈 스택을 생성하고 반환한다;
    Create and return an empty stack with stack size maxStackSize
```
   
// stack은 0개 이상의 원소를 갖는 스택   
// itme은 스택에 삽입되는 원소   
// maxStackSize는 스택의 최대 크기를 정의하는 정수   
- stack is a stack with zero or more elements   
- itme is an element that is inserted into the stack   
- maxStackSize is an integer that defines the maximum size of the stack   
   
#### Push operation   
// Push 연산   
   
```c
Stack Push(stack, item) ::= 
    if (StackIsFull(stack))
        then {
            Prints 'stackFull';
        }
    else {
        // 스택의 가장 위에 item을 삽입하고, 스택을 반환한다;
        Insert the item at the top of the stack, and return the stack;
    }
```
   
#### Pop operation   
// Pop 연산   
   
```c
Element Pop(stack) ::=
    if (StackIsEmpty(stack))
        then {
            Prints 'stackFull';
        }
    else {
        // 스택의 가장 위에 있는 원소(element)를 삭제하고 반환한다;
        Delete and return the element at the top of the stack;
    }
```
   
#### StackIsFull, StackIsEmpty operation   
// StackIsFull, StackIsEmpty 연산   
   
```c
Boolean StackIsFull(stack, maxStackSize) ::=
    if((Number of elements in the stack) == maxStackSize)
        then { Return 'TRUE'; }
    else { Return 'FALSE'; }
```
   
```c
Boolean StackIsEmpty(stack) ::=
    if (stack == CreateStack(maxStackSize))
        then { Return 'TRUE'; }
    else { Return 'FALSE'; }
```
   
<br />
### Application of a Stack   
// 스택의 응용   
   
// 변수에 대한 메모리의 할당과 수집을 위한 시스템 스택   
// 서브루틴 호출 관리를 위한 스택   
// 연산자들 간의 우선순위에 의해 계산 순서가 결정되는 수식 계산   
// 인터럽트의 처리와 되돌아갈 명령 수행 지점을 저장하기 위한 스택   
// 컴파일러, 순환 호출 관리   
- System stack for allocating and collecting memory for variables   
- Stack for managing subroutine calls   
- Calculation of a expression whose order of calculation is determined by priorities between operators   
- Stack to store the processing of interrupts and the point of command execution to return to   
- Compilers, Managing Recurisive Call   
   
// 시스템 스텍 (system stack)   
// - 변수에 대한 메모리의 할당과 수집을 위해 운영체제가 관리하는 스택   
- System stack   
  - Stack managed by the operating system for allocating and collecting memory for variables   
   
<br />
### Operation of the Stack   
// 스택의 연산   
   
#### Delete operation of stack   
// 스택의 삭제 연산   
   
// 'top--'에서 사용된 '--' 연산자의 위치에 따라 연산의 적용 순서가 달라질 수 있음   
- The order of application of the operation may vary depending on the position of the '--' operator used in 'top--'   
   
- Example   
   
```c
int a, b;
a = 5;
b = a--;
```
   
- Result   
   
```
a = 4
b = 5
```
   
- Example   
   
```c
int a, b;
a = 5;
b = --a;
```
   
- Result   
   
```
a = 4
b = 4
```
   
```c
// 계산 결과는 같으나 반영되는 순서가 다름
// The calculation results are the same, but the order of reflection is different
a-- == a - 1
--a == a - 1
```
   
#### Creating a Stack   
// 스택의 생성   
   
```c
#define STACK_SIZE 10
typedef int element;
element stack[STACK_SIZE];
int top = -1;
```
   
#### Delete operation of stack   
// 스택의 삭제 연산   
   
// 스택의 가장 위에 있는 원소를 삭제하는 연산   
- Operation to delete the top element of the stack   
   
```c
int pop() {
    if (top == -1)
        return StackIsEmpty();
    else return stack[top--];
}
```
   
#### Insertion Operation of stack   
// 스택의 삽입 연산   
   
// 스택의 가장 위에 있는 원소 중에 원소 하나를 추가하는 연산   
- The operation of adding one element to the top of the stack   
   
```c
void push(int itme) {
    if (top >= STACK_SIZE - 1)
        return STackIsFull;
    else stack[++top] = item;
}
```
   
<br />
### Prefix, Postfix and Infix notations of the four arithmetic operations   
// 사칙연산식의 전위·후위·중위 표현   
   
#### The calculation of expressions   
// 수식의 계산   
   
// 연산자의 계산 우선순위를 생각해야 함   
- Need to consider operator's computational priority   
   
- A + B * C + D   
  - ((A + (B * C)) + D)   
   
#### How to mark an expression   
// 수식의 표기 방법   
   
// 중위 표기법   
// - 연산자를 피연산자 사이에 표기하는 방법   
// - 일반적으로 가장 많이 사용하는 표기 방법   
- Infix notation   
  - Indicate operator between operands   
  - This is the most commonly used notation method   
  - `A + B`   
   
// 전위 표기법   
// - 연산자를 피연산자 앞에 표기하는 방법   
- Prefix notation   
  - Indicate operator before operands   
  - `+ A B`   
   
// 후위 표기법   
// - 연산자를 피연산자의 뒤에 표기하는 방법   
- Postfix notation   
  - Indicate operator after operands   
  - `A B +`   
   
#### Prefix notation   
// 전위 표기법   
   
`A + B => + AB`   
   
```c
( A - ( ( B + K ) / D ) )
→ ( A - ( ( + B K ) / D ) )
→ ( A - ( / ( + B K ) D ) )
→ - A ( / ( + B K ) D )
```
   
#### Postfix notation   
// 후위 표기법   
   
`A + B => AB +`   
   
```c
( A - ( ( B + K ) / D ) )
→ ( A - ( ( B K + ) / D ) )
→ ( A - ( ( B K + ) D / ) )
→ A ( ( B K + ) D / ) -
→ A B K + D / -
```
   
#### How to convert the Postfix notation of the Infix notation   
// 중위 표기식의 후위 표기식 변환 방법   
   
// 먼저 중위 표기식을 연산자의 우선순위를 고려하여 (피연산자, 연산자, 피연산자)의 형태로 괄호로 묶어줌   
// 각 계산뭉치를 묶고 있는 괄호 안에서 연산자를 계산뭉치의 가장 오른쪽으로 이동시킴   
// 각 계산뭉치를 하나의 피연산자로 고려하여 위를 반복함   
// 괄호를 모두 제거함   
- The Infix notation is grouped in parentheses in the form of (operand, operator, operand), taking into account the operator's priority   
- Move the operator to the far right of the computational bundle in parentheses that bind each batch of computations   
- Repeat above considering each batch of calculations as one operand   
- Remove all parentheses   
   
```c
  ( ( A - ( B / C ) ) - ( D * E ) )
→ ( ( A ( B C / ) - ) ( D E * ) - )
→ A B C / - D E * -
```
   
#### Computational Algorithm of Postfix notation   
// 후위 표기식의 계산 알고리즘   
   
// `3 + 6 * 9`를 후위 표기식으로 변환하면 `369*+` 가 됨   
- If '3 + 6 * 9' is converted into a Postfix notation, it becomes '369*+'   
   
```c
// 후위 표기식 (369*+) 을 계산하는 연산
// Operation to calculate the Postfix notation (369*+)
element evalPostfix(char *exp) {
    int oper1, oper2, value, i = 0;
    int length = strlen(exp);
    char symbol;
    top = -1;

    for(i = 0; i < length; i++) {
        symbol = exp[i];
        
        if(symbol != '+' && symbol != '-' && symbol != '*' && symbol != '/') {
            value = symbol - '0';    // a function for converting character into number
            push(value);
        } else {
            oper2 = pop();
            oper1 = pop();
            switch (symbol) {
                case '+' : push(oper1 + oper2); break;
                case '-' : push(oper1 - oper2); break;
                case '*' : push(oper1 * oper2); break;
                case '/' : push(oper1 / oper2); break;
            }
        }
    }

    return pop();
}
```
   
<br />
<cite>출처 : 한국방송통신대학교 컴퓨터과학과</cite>
