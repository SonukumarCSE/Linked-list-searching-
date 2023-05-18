# Linked-list-searching-
search in a linked list.
    # include <iostream>
    using namespace std;

    struct Node 
    {
        int data;
        Node *next;
        Node(int x)
        {
            data = x;
            next = NULL;
        }
    };

    void printlist(Node *head)
    {
        Node *curr=head;
        while(curr!=NULL)
        {
            cout<<curr->data<<" ";
            curr = curr->next;
        }
    }

    void rprintlist(Node *head)
    {
        if(head == NULL)
            return ;
        cout<<head->data <<" ";
        rprintlist(head->next);
    }

    int search(Node *head,int x)
    {
        Node *curr = head;
        int pos=0;
        while(curr!=NULL)
        {
            if(curr->data == x)
                return pos+1;
            pos++;
            curr = curr->next;
        }
    }

    int main()
    {
        Node *head = new Node(10);
        Node *temp1 = new Node(20);
        Node *temp2 = new Node(30);
        head->next = temp1;
        temp1->next = temp2;
        printlist(head);
        cout<<endl;
        rprintlist(head);
        cout<<search(head,20)<<" ";
        cout<<search(head,15);
        return 0;
    }
