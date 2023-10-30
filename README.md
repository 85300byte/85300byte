#include <stdio.h>
#include <stdlib.h>

#define MAX 5 // Maximum number of elements that can be stored

int top = -1;
char stack[MAX];

void push();
void pop();
void display();

int main()
{
    int ch;
    while (1)
    {
        printf("\n*** Stack Menu ***");
        printf("\n\n1.Push\n2.Pop\n3.Display\n4.Exit");
        printf("\n\nEnter your choice(1-4): ");
        scanf("%d", &ch);

        // Clear input buffer
        while (getchar() != '\n');

        switch (ch)
        {
        case 1:
            push();
            break;
        case 2:
            pop();
            break;
        case 3:
            display();
            break;
        case 4:
            exit(0);
        default:
            printf("\nWrong Choice!! Please enter a number between 1 and 4.\n");
        }
    }

    return 0;
}

void push()
{
    char val;
    if (top == MAX - 1)
    {
        printf("\nStack is full!! Cannot push more elements.\n");
    }
    else
    {
        printf("\nEnter character to push: ");
        scanf(" %c", &val);

        // Clear input buffer
        while (getchar() != '\n');

        top = top + 1;
        stack[top] = val;
        printf("Element '%c' pushed successfully.\n", val);
    }
}

void pop()
{
    if (top == -1)
    {
        printf("\nStack is empty!! Cannot pop elements.\n");
    }
    else
    {
        printf("\nDeleted element is '%c'\n", stack[top]);
        top = top - 1;
    }
}

void display()
{
    int i;
    if (top == -1)
    {
        printf("\nStack is empty!!\n");
    }
    else
    {
        printf("\nStack is...\n");
        for (i = top; i >= 0; --i)
            printf("'%c'\n", stack[i]);
    }
}