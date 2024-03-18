There are many topics and functions lumped under the term advance io include:

* nonblocking I/O
* record locking
* I/O multiplexing
* asynchronous I/O
* readv/writev functions
* memory mapped I/O

# Nonblocking I/O

There are two system call: the "slow" ones and the other. The "slow" system call are those can block forever. They include:

* Read can block forever if data isn't present with certain file type (pipes, )
