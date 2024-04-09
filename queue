#define MAX_QUEUE 100
#include <stdio.h>
#include <stdlib.h> // exit 함수를 사용하기 위해 추가


typedef int Data;

typedef struct {
    int front, rear;
    Data items[MAX_QUEUE];
} Queue;

void InitQueue(Queue* pqueue); // 초기화
bool IsFull(Queue* pqueue); // 가득 찼는지 확인
bool IsEmpty(Queue* pqueue); // 비었는지 확인
Data Peek(Queue* pqueue); // 맨 앞의 원소 반환
void EnQueue(Queue* pqueue, Data item); // 삽입
void DeQueue(Queue* pqueue); // 삭제

int main() {
    Queue myQueue;
    InitQueue(&myQueue);

    // 큐에 데이터 삽입
    EnQueue(&myQueue, 10);
    EnQueue(&myQueue, 20);
    EnQueue(&myQueue, 30);

    // 큐에서 데이터 확인 후 출력
    printf("Peek: %d\n", Peek(&myQueue));

    // 큐에서 데이터 제거
    DeQueue(&myQueue);

    // 큐의 모든 데이터 출력
    printf("Queue contents:\n");
    while (!IsEmpty(&myQueue)) {
        printf("%d ", Peek(&myQueue));
        DeQueue(&myQueue);
    }
    printf("\n");

    return 0;
}

void InitQueue(Queue* pqueue) {
    pqueue->front = pqueue->rear = 0;
}

bool IsFull(Queue* pqueue) {
    return pqueue->front == (pqueue->rear + 1) % MAX_QUEUE;
}

bool IsEmpty(Queue* pqueue) {
    return pqueue->front == pqueue->rear;
}

Data Peek(Queue* pqueue) {
    if (IsEmpty(pqueue))
        exit(1);
    return pqueue->items[pqueue->front];
}

void EnQueue(Queue* pqueue, Data item) {
    if (IsFull(pqueue))
        exit(1);
    pqueue->items[pqueue->rear] = item;
    pqueue->rear = (pqueue->rear + 1) % MAX_QUEUE;
}

void DeQueue(Queue* pqueue) {
    if (IsEmpty(pqueue))
        exit(1);
    pqueue->front = (pqueue->front + 1) % MAX_QUEUE;
}
