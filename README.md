# Hirschberg
Hirschberg Algo Implementation

Done by:
  Dmitry Yurchanka dmitryy2@illinois.edu
  Benji Chung bjchung3@illinois.edu
  Nisha Janamanchi nishaj3@illinois.edu


This Python notebook file implements the Hirschberg linear space complexity global alignment algorithm. It was benchmarked against the Needleman-Wunsch, homework 1 from BIOE 466, implementation to test the time complexity and the space complexity.

How to use:

  Get alignment and score:
    Input 2 strings that you want to align at the bottom of the notebook, in the "print(hirschberg("", "", delta, mismatch))", and run everything. 
    The function returns the optimal alignment of both of the strings together with a score for the alignment. The mismatch penalty can be altered
    by changing the mismatch value. Same can be done with the bonus for matches to make custom scoring functions.

  Test time complexity:
    Uncomment "# start = time.time(),"# end = time.time()," amd "# print(end - start)."
    Put in your desired string into the Hirschberg call, and the function will automatically 
    return the time that it took to get from the start of it to the end. This is the unofficial
    way that time complexity was tested between the Needleman-Wunsch and Hirschberg. The testing showcased
    that the time complexity of both are roughly O(n^2)
    https://docs.python.org/3/library/time.html#time.time
    
  Test space complexity:
    Uncomment "tracemalloc.start()," "print(tracemalloc.get_traced_memory())," and   
    "tracemalloc.stop()." The print out statement returns two values, the first one
    is the average space used, and the second one is the maximum space used. The second value
    was used to showcase that the space complexity for the Needleman-Wunsch was O(n^2)
    versus O(n) for Hirschberg.
    https://docs.python.org/3/library/tracemalloc.html
    https://www.geeksforgeeks.org/monitoring-memory-usage-of-a-running-python-program/
    

There are several test strings that are provided below the main function. These can be compared for alignment against any other global alignment algorithms. This visualizer was one of the ones to test smaller test cases https://bioboot.github.io/bimm143_W20/class-material/nw/ .


Breakdown of Code:
  Hirschberg ~ main recursive function called
    handles base cases that might show up
    runs the forward and back alignment to calculate i* to start the divide and conquer step
    call 2 more Hirschberg algorithms as the recursive step
    returns the alignments + the score produced

