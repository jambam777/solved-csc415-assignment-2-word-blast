Download Link: https://assignmentchef.com/product/solved-csc415-assignment-2-word-blast
<br>
For this assignment, your program is to read War and Peace (a text copy is included with this assignment) and it is to count all the words that are 6 or more characters long.

BUT, it is to do this using threads.  Each thread will take a chunk of the file and process it, returning it’s results to the main which tallies (or if you directly tally to shared memory, that is okay) and then the main will print the top ten words and the number of times that word appears in the text.

Your program should take two parameters on the command line:  FileName  and ThreadCount

FileName is the name of the file to read – WarAndPeace.txt

ThreadCount is the number of threads you should spawn to evenly divide the work.

That is to say – if the parameter is 1, the entire file would be read and processed by one thread.  If the parameter is 5, then you would divide the file into 5 equal parts (accounting for rounding on the last part).  So thread one would take the first 1/5 of the file, thread 2 the second fifth and so on.  But, these threads should all be launched together in a loop. So that they can execute in parallel.

#include &lt;time.h&gt; in your code and in main, include the code below in your main.  This will display how much time your program takes.  Your submission should include a run with 1 thread, 2 threads, 4 threads, and 8 threads.  How do the time compare?

struct timespec startTime;     struct timespec endTime;

clock_gettime(CLOCK_REALTIME, &amp;startTime);

&lt;YOUR CODE IN MAIN HERE&gt;

clock_gettime(CLOCK_REALTIME, &amp;endTime);  time_t sec = endTime.tv_sec – startTime.tv_sec;  long n_sec = endTime.tv_nsec – startTime.tv_nsec;  if (endTime.tv_nsec &lt; startTime.tv_nsec)

{

–sec;

n_sec = n_sec + 1000000000L;

}

printf(“Total Time was %ld.%09ld seconds
”, sec, n_sec);

Do not forget to protect critical sections.

You should submit your source code file(s) along with a short writeup in PDF format that includes a description of what you did and the compilation and execution output from your program. Your execution output should include at least 4 runs, 1 thread, 2 threads, 4 threads, and 8 threads, along with how those times compare in your writeup.


