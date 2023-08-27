# Linked List
class Node:
   
   def __init__(self, data = None, next = None):
       self.data = data
       self.next = next 
       
    
class LinkedList:
   def __init__(self): 
       self.head = None
      
   def insertAtBeginning(self, data):
       node = Node(data, self.head)
       self.head = node 
   
   def printLinkedList(self ):
   
       if self.head == None:
          print("LinkedList is empty")
          return 
       s = ''
       itter = self.head
       while(itter):
          s += str(itter.data) + "--->" 
          itter = itter.next
       print(s,'None', sep = '')   
       
   def insertAtEnd(self, data):
       node = Node(data)
       if self.head is None:  
        self.head = node   
        return
       
       itter = self.head 
       
       while(itter.next):
          itter = itter.next 
       itter.next = node
       
   def insertValues(self, values):
       
       for val in values:
           self.insertAtEnd(val)
   
   def getLength(self):
       c = 0 
       itter = self.head
       while(itter):
         itter = itter.next
         c += 1
       return c
   def removeAtIndex(self, index):
       if index < 0 or index >= self.getLength():
           raise Exception("Invalid Index") 
       else:
           c = 0
           itter = self.head
           if index == 0:
               self.head = itter.next
               return
           while(itter):
               if c == index:
                   prev.next = itter.next 
                   break
               prev = itter
               itter = itter.next 
               c += 1 
   def insertAtIndex(self, index, data):
    if index < 0 or index > self.getLength():
        raise Exception("Invalid Index")
    else:
        c = 0
        itter = self.head
        prev = None  # Initialize 'prev' outside the loop
        while itter:
            if c == index:
                node = Node(data)
                if prev:  # Inserting at a non-head index
                    prev.next = node
                else:  # Inserting at the head
                    self.head = node
                node.next = itter
                break
            prev = itter  # Update 'prev' before moving 'itter'
            itter = itter.next
            c += 1
               
           
if __name__ == "__main__":

  ll = LinkedList()
  ll.insertAtBeginning(10)
  ll.insertAtBeginning(20)
  ll.insertAtBeginning(30)
  ll.insertAtBeginning(40)
  ll.insertAtBeginning(50)
  ll.insertAtBeginning(60)
  ll.insertAtBeginning(70)
  ll.insertAtEnd(0)
  ll.insertValues([80, 90, 100 , 110 , 120 , 130, 45349580328])
 
  print(ll.getLength())
  ll.printLinkedList()
  ll.removeAtIndex(10)
  ll.removeAtIndex(13)
  ll.printLinkedList()
  ll.insertAtIndex(10, 33333)
  ll.printLinkedList()
  
