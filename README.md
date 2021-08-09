EXPERIMENT-2
#include<stdio.h>
#include<stdlib.h>
#define capacity 1000
int top=-1,top1=-1,stack[capacity],stack1[capacity],count=0,i;

void enqueue(int elem);
void dequeue();
void push1(int elem);
void push2(int elem);
int pop1();
int pop2();
void display();

void main()
{
    int choise=0,elem=0;
    while(1)
    {
        printf("\n1.ENQUEUE");
        printf("\n2.DEQUEUE");
        printf("\n3.DISPLAY");
        printf("\n4.EXIT");
        printf("\n");
        printf("Enter Your Choise: ");
        scanf("%d",&choise);
        switch(choise)
        {
            case 1: printf("Enter a value: ");
                     scanf("%d",&elem);
                     enqueue(elem);
                     break;
            case 2: dequeue();
                     break;
            case 3: display();
                     break;
            case 4: exit(0);
            default: printf("\nInvalid: ");
                     break;
        }
    }
    
}

void push1(int elem)
{
    if(top==capacity-1)
        printf("\nQueue is Full");
    else
        ++top;
        stack[top]=elem;
}
void push2(int elem)
{
    if(top1==capacity-1)
        printf("\nQueue is Full");
    else
        ++top1;
        stack1[top1]=elem;
}

void enqueue(int elem)
{
    push1(elem);
    count++;
    printf("\n%d Enqueued Sussfully\n",elem);
}
int pop1()
{
    return stack[top--];
}
int pop2()
{
    return stack1[top1--];
}

void dequeue()
{
    int a,b;
    if(top==-1&&top1==-1)
    {
        printf("\nQueue is Empty");
    }
    else
    {
        for(i=0;i<count;i++)
        {
            a=pop1();
            push2(a);
        }
        b=pop2();
        printf("\nDequeued Element is: %d\n",b);
        count--;
        for(i=0;i<count;i++)
        {
           a= pop2();
           push1(a);
        }
    }
}

void display()
{
    printf("\n");
    printf("Name:- sirisha");
    printf("\nRollNo:- 221810305055");
    printf("\nElements in the Queue are: ");
    for(i=0;i<=top;i++)
    {
        printf("%d ",stack[i]);
    }
    printf("\n");
}

