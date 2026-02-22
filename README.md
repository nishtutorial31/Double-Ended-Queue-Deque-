#include <stdio.h>
#define MAX 5

int dq[MAX];
int front = -1, rear = -1;

void insertRear(int x) {
    if (rear == MAX - 1)
        printf("Overflow\n");
    else {
        if (front == -1) front = 0;
        dq[++rear] = x;
    }
}

void insertFront(int x) {
    if (front == 0)
        printf("Overflow\n");
    else {
        if (front == -1) front = rear = 0;
        else front--;
        dq[front] = x;
    }
}

void display() {
    for (int i = front; i <= rear; i++)
        printf("%d ", dq[i]);
    printf("\n");
}

int main() {
    insertRear(10);
    insertRear(20);
    insertFront(5);
    display();
    return 0;
}
