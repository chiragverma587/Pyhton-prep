### 1.[Get Nth node in a linked list](https://practice.geeksforgeeks.org/problems/node-at-a-given-index-in-linked-list/1)
    def getNth(head, k):
    # Code here
    current=head
    count=1
    while(current):
        if(count==k):
            return current.data
        current=current.next
        count+=1
