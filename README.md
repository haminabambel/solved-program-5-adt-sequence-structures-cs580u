Download Link: https://assignmentchef.com/product/solved-program-5-adt-sequence-structures-cs580u
<br>
<h3><u>Driver Code and Test Input Files</u></h3>

<h3>●       Provided Files</h3>

<ul>

 <li><a href="https://drive.google.com/open?id=199qt7aUCXm6Iysn5HqjNBZh8WpMdo0NJ">c </a>//This is the Driver Code, to be linked with your functions.</li>

</ul>

<h3><u>Grading Rubric</u></h3>

<strong><em>TOTAL: 25 points</em></strong>

<h2>●       Part A (10 points):</h2>

<ul>

 <li>[2 pts] Test #1 Passed: newVector function creates a vector with properly initialized values</li>

 <li>[2 pts] Test #2-4 Passed: inserting into the vector passes all tests</li>

 <li>[2 pts] Test #5-7 Passed: reading from vector passes all tests</li>

 <li>[2 pts] Test #8-9 Passed: removing from vector passes tests</li>

 <li>[2 pts] Test #10 Passed: deleting vector does not result in memory leak</li>

</ul>

<h2>●       Part B (10 points):</h2>

<ul>

 <li>[2 pts] Test #11 Passed: newList function creates a list with properly initialized values</li>

 <li>[2 pts] Test #12 Passed: inserting into list at index passes test</li>

 <li>[2 pts] Test #13 Passed: reading from list at index passes test</li>

 <li>[4 pts] Test #14 Passed: removing and deleting from list at index passes test</li>

</ul>

<ul>

 <li><strong>Part C (5 points):</strong>

  <ul>

   <li>[5 pts] implements profileInsert, profileRead, and profileRemove as described</li>

  </ul></li>

</ul>

<h2>●       Style Guidelines and Memory Leaks</h2>

<h2>○       <em>You will lose significant points for the following:</em></h2>

<h2>■       Makefile does not have requested format and labels (-5 points)</h2>

<h2>■       Does not pass Valgrind Tests (-5 points)</h2>

<h2>■       Does not follow requested program structure and submission format (-5 points)</h2>

<h3><u>Guidelines</u></h3>

This is a pair programming assignment. You and a partner can divide up the work. Although both of you may not work on all parts of the program you should understand and be able to fully explain every portion of the code. Outside of your team, it is permissible to consult with classmates to ask general questions about the assignment, to help discover and fix specific bugs, and to talk about high level approaches in general terms. It is not permissible to give or receive answers or solution details from fellow students.




You may research online for additional resources; however, you may not use code that was written specifically <em>to</em> solve the problem you have been given, and you may not have anyone else help you or your partner write the code or solve the problem. You may use code snippets found online, providing that they are appropriately and clearly cited, within your submitted code.




If you or your partner are found to have plagiarized any part of the assignment, both will receive a 0 and be reported.

<em> </em>

<em>By submitting this assignment, you agree that you have followed the above guidelines regarding collaboration and research.</em>




<strong><u> </u></strong>

For this program you and partner are going to build both a dynamic array (vector) and a linked list. Each data structure will be tested to ensure the validity of its operations. Once that is complete and you know your data structures are working, we are going to test them against each other for performance (this is the fun part).




To make our code more portable, we are going to wrap our data in a Data struct, and build all our operations around this data type. In a header file, data.h, create a struct, Data, which contains the following:

<h1>●       a single integer called, ‘value’</h1>

Since we are going to be passing by value, we will not need a constructor or destructor.




Part A: Vectors

<h1>●       You must break up your code into vector.h and vector.c according to the conventions we discussed in class.</h1>

<h1>●       Create a dynamic array data structure, Vector. You must create your struct and internal array on the heap (using malloc). Your dynamic array should have, at minimum, the following:</h1>

<ul>

 <li><em>data</em>: A pointer to a Data struct array</li>

 <li><em>current_size</em>: an unsigned integer containing the current size</li>

 <li><em>max_size</em>: an unsigned integer containing the maximum capacity</li>

 <li><em>void (*insert)(Vector * array, int index, Data value): </em>a function pointer to an insert function</li>

 <li><em>Data * (*read)(Vector * array, int index):</em> a function pointer to an read function</li>

 <li><em>void (*remove)(Vector * array, int index):</em> a function pointer to an delete function</li>

 <li><em>void (*delete)(Vector * array):</em> a function pointer to a destructor</li>

</ul>

<ul>

 <li>You may add additional attributes if you need them</li>

</ul>

<ul>

 <li>You must create the following functions for your Vector

  <ul>

   <li>Constructor – initializes the vector struct attributes and returns a pointer to a Vector struct created on the heap

    <ul>

     <li>Vector * newVector()</li>

    </ul></li>

  </ul></li>

</ul>

<em>NOTE: The remaining function names are suggestions since the driver code calls them all via function pointers</em>

<ul>

 <li>Insert – inserts an element at the specified index. Use the 2n+1 geometric expansion formula to increase the size of your list if the index is out of the current bounds.

  <ul>

   <li>void insertVector(Vector * array, int index, Data value);</li>

  </ul></li>

 <li>Remove – deletes an element from the list at the specified index.

  <ul>

   <li>void removeVector(Vector * array, int index);

    <ul>

     <li>You must implement true deletion, which will reduce the size of the vector by 1</li>

    </ul></li>

   <li>Read – return <strong><em>the pointer to the data struct</em></strong> from the specified index, return NULL if the index is out of bounds, and a data struct with the value set to -1 if the index has not been initialized

    <ul>

     <li>Data * readVector(Vector * array, int index);</li>

    </ul></li>

   <li>Destructor – upon exiting, be sure all memory has been freed by calling

    <ul>

     <li>void * deleteVector which free’s all struct memory

      <ul>

       <li>You should return a NULL pointer from any delete procedure. This is just a convention.</li>

      </ul></li>

    </ul></li>

  </ul></li>

</ul>




Part B: Linked Lists

<ul>

 <li>You must break up your code into list.h and list.c according to the conventions we discussed in class.Your node struct must have the following:

  <ul>

   <li><em>next/prev:</em> A pointer to the next and previous nodes</li>

   <li><em>data:</em> A data object <strong>(note: not a pointer)</strong></li>

  </ul></li>

</ul>

Your list struct must have the following:

<ul>

 <li><em>head/tail:</em> A pointer to nodes at the head and tail</li>

 <li><em>void (*insert)(List *, int, Data):</em> a function pointer to an insert function</li>

 <li><em>Data * (*read)(List *, int): </em>a function pointer to a read function</li>

 <li><em>void (*remove)(List *, int): </em>a function pointer to an delete function</li>

 <li><em>void (*delete)(List *):</em> a function pointer to a destructor</li>

</ul>

<ul>

 <li>Create a doubly linked list using a list and node structs. You must create your linked list on the heap (using malloc). Your linked list should have the following operations:

  <ul>

   <li>Constructor – initializes the linked list struct:

    <ul>

     <li>List * newList()

      <ul>

       <li>A pointer to a head and tail node, both initialized to NULL</li>

       <li>set function pointers to the appropriate functions</li>

       <li>returns a pointer to a List struct created on the heap</li>

      </ul></li>

     <li>Insert – inserts an element at a specified index in the list.

      <ul>

       <li>void insertList(List * list, int index, Data value);

        <ul>

         <li>Adds the Data to the specified index</li>

         <li>If the index is out of bounds, adds the data to the end of your list.</li>

        </ul></li>

       <li>Delete – deletes an element from a specified index in the list.

        <ul>

         <li>void removeData(List * list, int index);

          <ul>

           <li>If the index is out of bounds, you should just return without doing anything.</li>

          </ul></li>

         <li>Read – returns a pointer to the data element stored in the list

          <ul>

           <li>Data * readData(List * list, int index);

            <ul>

             <li>If the index is out of bounds, return a NULL pointer</li>

            </ul></li>

          </ul></li>

        </ul></li>

      </ul></li>

    </ul></li>

  </ul></li>

</ul>

Part C: Profiling Your Code

<h1>●       Create another file called profile.c/.h. Inside this file you should implement 3 functions that profile your vector and list data structures. You must ensure that only the relevant code is being profiled. Example profiling code is provided:</h1>

<ul>

 <li>#include &lt;time.h&gt;#include &lt;sys/time.h&gt;/* timeval, gettimeofday() */…struct timeval start, stop;gettimeofday(&amp;start, NULL);//code to be profiled…gettimeofday(&amp;stop, NULL);time_t start_time = (start.tv_sec* 1000000) + start.tv_usec;time_t stop_time = (stop.tv_sec* 1000000) + stop.tv_usec;float profile_time = stop_time – start_time;</li>

</ul>

<h1>●       Print the results to stdout. The description of each function is below.</h1>

<ul>

 <li>void profileInsert(Vector *, List *)

  <ul>

   <li>Insert 1000 data objects. The data objects should contain integers in increasing value, i.e. 1,2,3, etc.</li>

   <li>Profile the insertion of the data objects for both the vector and the list separately, then print the results.</li>

  </ul></li>

 <li>void profileRead(Vector *, List *)

  <ul>

   <li>Search for 100 random data objects in your sequences. Try to use as similar search algorithms as possible for your search. Your search algorithm can assume unordered data.</li>

   <li>Profile the read time of the data objects for both the vector and the list separately, then print the results.</li>

  </ul></li>

 <li>void profileRemove(Vector *, List *)

  <ul>

   <li>Remove for 100 random data objects in your sequences.</li>

   <li>Profile the read time of the data objects for both the vector and the list separately, then print the results.</li>

  </ul></li>

</ul>

Part D: Submission




<ul>

 <li>Required code organization:

  <ul>

   <li>c //Provided Driver Code</li>

   <li>h/c

    <ul>

     <li>profileInsert(Vector *, List *)</li>

     <li>profileRead(Vector *, List *)</li>

     <li>profileRemove(Vector *, List *)</li>

    </ul></li>

   <li>h

    <ul>

     <li>Data struct

      <ul>

       <li>value (int)</li>

      </ul></li>

     <li>h/c – Your header file should have the following function declarations:

      <ul>

       <li>Vector struct

        <ul>

         <li>data (Data)</li>

         <li>current_size (int)</li>

         <li>int max_size (int)</li>

         <li>void (*insert)(struct Vector *, int, Data);</li>

         <li>Data * (*read)(struct Vector *, int);</li>

         <li>void (*remove)(struct Vector *, int);</li>

         <li>void * (*delete)(struct Vector *);</li>

        </ul></li>

       <li>Vector * newVector();</li>

      </ul></li>

     <li>h/c – Your header file should have (at minimum) the following function declarations:

      <ul>

       <li>Node struct

        <ul>

         <li>data (Data)</li>

         <li>next (Node *)</li>

         <li>prev (Node *)</li>

        </ul></li>

       <li>List struct

        <ul>

         <li>head (Node *)</li>

         <li>tail (Node *)</li>

         <li>void (*insert)(struct List * , int , Data );</li>

         <li>Data * (*read)(struct List * , int );</li>

         <li>void (*remove)(struct List * , int );</li>

         <li>void (*delete)(struct List * );

          <ul>

           <li>deletes the entire list from memory</li>

          </ul></li>

         <li>List * newList();</li>

        </ul></li>

       <li>makefile

        <ul>

         <li><em>You must have the following labels in your makefile:</em>

          <ul>

           <li>all – to compile all your code to an executable called ‘<strong>program5</strong>’ (no extension). <strong>Do not run</strong>.</li>

           <li>run – to compile if necessary and run</li>

           <li>checkmem – to compile and run with valgrind</li>

           <li>clean – to remove all executables and object files</li>

          </ul></li>

         <li>While inside your program 5 folder, create a zip archive with the following command

          <ul>

           <li>zip -r &lt;username&gt;_program5 &lt;list of required files&gt;

            <ul>

             <li>This creates an archive of all file and folders in the current directory called &lt;username&gt;_program5.zip</li>

             <li><strong>Do not zip the folder itself, only the files required for the lab</strong></li>

            </ul></li>

           <li>Upload the archive to Blackboard under Program 5.</li>

          </ul></li>

        </ul></li>

      </ul></li>

    </ul></li>

  </ul></li>

</ul>