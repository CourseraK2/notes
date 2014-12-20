Inter-process Communication
===========================

Activity of sharing data across multiple and specialized processes using some kind of communication protocol.
A simple example is our compute cluster, containing a collection of ‘clients’ and ‘servers’ communicating using IPC.

Unix pipes are possibly the more famous IPC:
```
DO THIS | THEN DO THIS
```

DO THIS is chained to ‘THEN DO THIS’  by a ”left associative” pipe. Just like in functional programming, data is passed from DO THIS to THEN DO THIS
In Unix when you do a pipe(), it creates an anonymous pipe with two new file open file descriptors: 1) Reading end 2) Writing end
Unix does a clever implementation to avoid data loss. If DO THIS is ‘transmitting’ data at 100 bytes/s while the input strength for THEN DO THIS
is only 50 bytes/s the remaining is held in a queue buffer. If the queue buffer is full, then DO THIS would be suspended until THEN DO THIS has cleared up part of the
buffer. Another key thing to note is that all the processes are running in parallel, programmiticallly, not sequentially.


Approaches
=========

* File
* Signal
* Socket
* Message Queue
* Pipe
* Named pipe
* Semaphore
* Shared Memory
* Message Passing
* Memory mapped
:q
