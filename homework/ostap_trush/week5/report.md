### Week 5 File Systems Homework

### You should use this doc as a template, fork the repository, answer the questions and send us the link to grade.

### Try to answer these questions yourself, without consulting Google too much. Once you are finished with answering these questions however, read more on all the concepts you do not understand well, and reread our presentation on the topic

---

1. Using only command-line programs (`ls`, `cd`) jump around your user directories. **What are some of the interesting options for these programs?**
ls:-a|-l|-la|  cd:~|/|..|.|-P|-L
1. Consider an i-node that contains 10 direct addresses to disk blocks. Disk Blocks are 1024 kb each. **What's the largest file size possible?**
10MB
1. **How are external devices represented in file systems in Unix-like systems?**
As characters/character special files
1. For a given class, the student records are stored in a file. The records are randomly accessed and updated. Assume that each student's record is of fixed size. **Which of the three allocation schemes (contiguous, linked and table/indexed) should be used?**
contiguous, becouse size is the fixed
1. One way to use contiguous allocation of the disk and not suffer from holes is to compact the disk every time a file is removed. Since all files are contiguous, copying a file requires a seek, a disk hand rotation, followed by the transfer at full speed. Writing the file back requires the same work. **Assuming a seek time of 5 msec, a rotational delay of 4 msec, a transfer rate of 80 MB/sec, an average file size of 8 KB, how long does it take to read a file into main memory and then write it back to the disk at a new location? Using these numbers, how long would it take to compact half of a 16-GB disk?**
The time required to transfer 8KB file is 0.09765625 msec so I will use 0.1 msec here
(5+4+0.1) * 2 = 18.2 msec - time to transfer 1 8KB file
8GB - 1048576 8KB files
result = 18.2 * 1048576 = 19084083.2 msec = 19084.0832 sec = 5.3 hours approximately
1. **Suggest a few real-world examples for devices that would work with contiguous file systems?**
Devices that always have the same file size saved(can't think of any examples)
Devices that always save approximately the same file size and type(Ebooks maybe?Idk) 
1. **Is it possible to recover the disk in the case that free space list is damaged?**
no becouse that memory will be occupied forever and computer will think that it is free
space but it is not 
1. **How many disk operations are necessary to get the file at `/home/$USER/Documents/history/foucault.txt` path?** Presume that we are located at the root (`/`), no i-node is cached and each i-node transition takes 1 disk operation.
5
1. In many \*nix systems, the i-nodes are kept at the start of the disk. An alternative design is to allocate an i-node when a file is created and put the i-node at the start of the first block of the file. **What are the tradeoffs of this approach?**
Maybe quicker data acsess, becouse the i-node is mush closer to the file.
Also the fact that the i-node is near the file itself and not somewhere far away.
