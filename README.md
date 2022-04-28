# Using Threads in Parallel with Spinlock and Mutex

This is a parallel hashtable (parallelhashtable.c) I worked on for my operating systems class. The code is meant to show errors with parallelism where when a thread writes to a spot in the table, is interrupted for another thread to write to that same spot, then regains control and finishes its write, there is an error where not all the slots in the table are full. 

Our task was to correct this problem using locks around critical sections of the code. In mutex.c, I used the C++ mutex API to place a mutex around each "bucket" that the threads would work with. This ensures that thread inserts will not result in missing key values, and that insert operations could be performed in parallel. I recreated this same functionality in spinlock.c, using the C++ spinlock API to place a spinlock around critical sections.
