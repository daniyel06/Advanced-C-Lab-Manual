EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

~~~
struct Node{
    int data; 
    struct Node *next;
}*head;

void search(int data)
{
 
 struct Node*temp=head;
 int flag=0;
 int i=0;
 while(temp->data!=data)
 {
     i++;
     if(temp->next!=NULL)
     temp=temp->next;
     else break;
     
 }
 if(temp->data==data)
 {
     printf("item %d found at location %d",data,i+1);
     flag=1;
 }
 if(flag==0)
 {
     printf("Item not found");
 }
 
    
}

~~~

Output:


![437709570-f7550e96-8620-4edd-830c-e0d8980901c7](https://github.com/user-attachments/assets/b2a1e37b-399e-4a08-90dc-c8cb256fbcb5)



Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
~~~
struct Node{
    int data; 
    struct Node *next;
}*head;


void insert(int data)
{
    struct Node* n=(struct Node*)malloc(sizeof(struct Node));
    struct Node* temp=head;
    n->data=data;
    n->next=NULL;
    if(head==NULL){
        
        head=n;
    }else{
        while(temp->next!=NULL){
            temp=temp->next;
        }
        temp->next=n;
        
    }
}

~~~

Output:

![437709642-927a06eb-7f98-4d8a-b790-7460787b7edb](https://github.com/user-attachments/assets/112ee17f-cc14-4093-81cb-844afcefa267)


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

~~~
struct Node
{
    struct Node *prev;
    struct Node *next;
    int data;
}*head;

void display()
{
    struct Node* temp=head;
    while(temp!=NULL)
    {
        printf("%d\n",temp->data);
        temp=temp->next;
    }
    
}

~~~

Output:
![437709772-266f7949-0aab-4e0a-bde3-4b9ce83cb3f3](https://github.com/user-attachments/assets/3d248bd3-f4d0-41b2-b6e0-68b024ab074f)




Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:
~~~
struct Node
{
    struct Node *prev;
    struct Node *next;
    float data;
}*head;

void insert(float data)
{
    struct Node* n=(struct Node*)malloc(sizeof(struct Node));
    struct Node* temp=head;
    n->data=data;
    n->next=NULL;
    if(head==NULL){
        head=n;
        return;
    }
    while(temp->next!=NULL){
        temp=temp->next;
    }
    temp->next=n;
    
    
}


~~~

Output:

![437709861-8914ba36-52fd-48a5-adf1-816f0721282e](https://github.com/user-attachments/assets/fa66db89-a305-4e4e-a92a-cd6e0c51a7c0)


Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:
~~~

struct Node
{
    int data; 
    struct Node *next;
}*head;
void display()
{
    struct Node* temp=head;
    while(temp!=NULL)
    {
        printf("%d ",temp->data);
        temp=temp->next;
    }
}
void insert(int data)
{
    struct Node* temp=head;
    struct Node* ptr=(struct Node*)malloc(sizeof(struct Node));
    ptr->data=data;
    ptr->next=NULL;
    if(head==NULL)
    {
        head=ptr;
    }else
    {
        while(temp->next!=NULL)        {
            temp=temp->next;
        }
        temp->next=ptr;
    }
}
void search(int data)
{
    int i=1;
    struct Node* temp=head;
    if(head==NULL)
    {
        printf("Elements not found");
    }else
    {
        while(temp!=NULL)
        {
            
            if(temp->data==data)
            {
                printf("item %d found at location %d\n",data,i);
                return;
            }
            i++;
            temp=temp->next;
        }
        printf("Item not found\n");
    }
}
void delete()
{
    struct Node* temp=head;
    if(head==NULL)
    {
        printf("UNDERFLOW");
    }else
    {
        head=head->next;
        free(temp);
        printf("Node deleted\n");
    }
    
}


~~~

Output:



![437710019-b87d5fe4-0a38-46a9-ad2e-e4d15de9af47](https://github.com/user-attachments/assets/67bfd427-9494-4681-85a7-ddd606f61418)




Result:
Thus, the function that deletes a given element from a linked list is verified successfully.
