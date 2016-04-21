# Cache

It's a simple light weight cache programmed in java designed to work in multithreaded environment. It is designed considering the fact that fetch should work fast even when parallel updates are in process. 

Use of blocking Deque is to implement peak() and take() methods. These methods usages Deque like a stack and take() methods usages it's blocking behaviour. 

Add() method is designed to make sure inserts in cache are sequential as consistency of peak() and take() depends on insertion time.

Clear() removes the expired elements from cache in background. It takes benefit of the fact that elements being expired are most likely to be at the end of the deque.

remove() method is not completely synchronised but take() and peak() are implemented considering this fact. Thus parallelism is achieved with consistency.

JUnit : is used for unit testing.
