# Stacks and Queues
---
## What is a stack?
Stack is a container of objects that are inserted and removed according to the last-in first-out (LIFO) principle. First, we need to create a class for stack to instantiate an object, then it can be implemented using the Node class or any as long as the used methods apply the principles of stack, so that each element inside a stack is a node.

### Stacks follow these concepts:
FILO: it stands for First In Last Out.
This means that the first item added in the stack will be the last item popped out of the stack.

LIFO: it stands for Last In First Out.
This means that the last item added to the stack will be the first item popped out of the stack.

### A stack should include the following:
+ Push - Nodes or items that are put into the stack are pushed.

	![push](https://www.javascripttutorial.net/wp-content/uploads/2016/08/JavaScript-Stack-Push-Operations.png)

+ Pop - Nodes or items that are removed from the stack are popped. When you attempt to pop an empty stack an exception will be raised.

	![pop](https://www.javascripttutorial.net/wp-content/uploads/2016/08/JavaScrippt-Stack-Pop.png)

+ Top - This is the top of the stack.

	![top](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/how-to-implement-stack-push-operation-cf97479ab11316c4.png)

+ Peek - When you peek you will view the value of the top Node in the stack. When you attempt to peek an empty stack an exception will be raised.

	![peek](https://qph.cf2.quoracdn.net/main-qimg-f22268230c00651b84db79c13bdb7ec9)

+ IsEmpty - used to check and verify if a Stack is empty or not. It returns True if the Stack is empty else it returns False.
---
## What is a queue?
Queue is a container of objects (a linear collection) that are inserted and removed according to the first-in first-out (FIFO) principle. First, we need to create a class for queue to instantiate an object, then it can be implemented using the Node class or any as long as it applies the principles of queue, so that each element inside a queue is a node. 

### Queues follow these concepts:
FIFO: it stands for First In First Out.
This means that the first item in the queue will be the first item out of the queue.

LILO: it stands for Last In Last Out.
This means that the last item in the queue will be the last item out of the queue.

### A queue should contain the following:
+ Enqueue - Nodes or items that are added to the queue.
+ Dequeue - Nodes or items that are removed from the queue. If called when the queue is empty an exception will be raised.

	![queue](https://www.javascripttutorial.net/wp-content/uploads/2016/08/JavaScript-Queue-Illustration.png)

**Note:** we can call the Rear other names such as BACK or TAIL.

+ Front - This is the front/first Node of the queue.
+ Rear - This is the rear/last Node of the queue.
+ Peek - When you peek you will view the value of the front Node in the queue. If called when the queue is empty an exception will be raised.

	![peek](https://dz2cdn1.dzone.com/storage/temp/8350689-fifo-queue.png)
	
+ IsEmpty - returns true when queue is empty otherwise returns false. For the first queue, when IsEmpty is called, it will return true, but for the other queues, it will return false.
![IsEmpty](https://cdn.programiz.com/sites/tutorial2program/files/queue.png)
