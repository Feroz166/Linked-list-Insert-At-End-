# Linked-list-Insert-At-End-

<blr>
  Author ~Mohammed Feroz
  <blr>
This repository demonstrates the implementation of inserting a node at the end of a singly linked list using the C programming language. A linked list is a dynamic data structure where elements (nodes) are connected using pointers, allowing efficient memory usage and flexible data management.


code
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node* next;
};
void insertAtEnd(struct node**head,int val)
{
    struct node* newnode=(struct node*)malloc(sizeof(struct node));
    newnode->data=val;
    newnode->next=NULL;
    if(*head==NULL)
    {
        *head=newnode;
        return;
    }
    else
    {
        struct node*temp=*head;
        while(temp->next!=NULL)
        {
            temp=temp->next;
        }
        temp->next=newnode;
    }
}
void display(struct node*head)
{
    struct node*temp=head;
    while(temp!=NULL)
    {
        printf("%d->",temp->data);
        temp=temp->next;
    }
    printf("NULL");
}
int main()
{
    struct node*head=NULL;
    int n, val;
    printf("enter the no of elements:");
    scanf("%d",&n);
    printf("\nEnter the elements:");
    for(int i=0;i<n;i++)
    {
        scanf("%d",&val);
        insertAtEnd(&head,val);
    }
    printf("\nLinkedlist:");
    display(head);
}
