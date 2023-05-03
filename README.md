Download Link: https://assignmentchef.com/product/solved-cs2110-timed-lab5-memory-allocation-in-c
<br>
For this assignment, you will implement a binary search tree using memory allocation in C. There are four methods to write: bst_add, bst_contains, and bst_destroy.

Pseudocode and detailed descriptions have been defined for each method inside of the javadocs in binary search tree.c.

<h2><a name="_Toc5267"></a>3.1         Binary Search Trees</h2>

A binary search tree is a node-based data structure with the following properties:

<ul>

 <li>each node has a maximum of two children.</li>

 <li>the left subtree of a node contains only nodes with values less than the value of the original node.</li>

 <li>the right subtree of a node contains only nodes with values greater than the value of the original node.</li>

 <li>the left and right subtrees must also be binary search trees.</li>

</ul>

In the example bst, you will notice that all children to the left of a parent node are of smaller value than the parent itself, and the children to the right of a parent node are of greater value than the parent itself. The basic process for memory allocation for a bst is not unlike the process used with linked lists, so feel free to reference Homework 8.

<h1><a name="_Toc5268"></a>4           Instructions</h1>

You will be editing ONLY binary search tree.c. We have defined the bst node struct in the binary search tree.h file. Instructions for each method have been provided in the javadocs for each method in binary search tree.c.

All #include directives have been included for you. Do not add any more includes. Doing so will result in point deductions that the tester will not reflect.

<h2><a name="_Toc5269"></a>4.1         Dependencies</h2>

There are some dependencies for running the tests.

If you are using Docker, re-run cs2110docker.sh to stop the old container, download updates to the image (which include these dependencies), and restart the container.

If you are using a VM, run

$ sudo apt install build-essential gdb valgrind pkg-config check

<h1><a name="_Toc5270"></a>5           Testing Your Work</h1>

<h2><a name="_Toc5271"></a>5.1         Debugging in C</h2>

We have provided you with a test suite to check your linked list that you can run locally on your very own personal computer. You can run these using the Makefile.

The given test cases are the same as the ones on Gradescope. Note that you will pass some of these tests by default. Your grade on Gradescope may not necessarily be your final grade as we reserve the right to adjust the weighting. However, if you pass all the tests and have no memory leaks according to valgrind, you can rest assured that you will get 100 as long as you did not cheat or hard code in values.

You will not receive credit for any tests you pass where valgrind detects memory leaks or memory errors. Gradescope will run valgrind on your submission, but you may also run the tester locally with valgrind for ease of use.

Printing out the contents of your structures can’t catch all logical and memory errors, which is why we also require you run your code through valgrind.

We certainly will be checking for memory leaks by using valgrind, so if you learn how to use it, you’ll catch any memory errors before we do.

Your code must not crash, run infinitely, nor generate memory leaks/errors.

Any test we run for which valgrind reports a memory leak or memory error will receive no credit.

If you need help with debugging, there is a C debugger called gdb that will help point out problems. See instructions in the Makefile section for running an individual test with gdb.

<h2><a name="_Toc5272"></a>5.2         Makefile</h2>

We have provided a Makefile for this assignment that will build your project. Here are the commands you should be using with this Makefile:

<ol>

 <li>To clean your working directory (use this command instead of manually deleting the .o files): make clean</li>

 <li>To run the tests without valgrind or gdb: make run-tests</li>

 <li>To run your tests with valgrind: make run-valgrind</li>

 <li>To debug a specific test with valgrind: make TEST=test name run-valgrind</li>

 <li>To debug a specific test using gdb: make TEST=test name run-gdb Then, at the (gdb) prompt:

  <ul>

   <li>Set some breakpoints (if you need to — for stepping through your code you would, but you wouldn’t if you just want to see where your code is segfaulting) with b suites/bst suite.c:420, or b binary search tree.c:69, or wherever you want to set a breakpoint</li>

   <li>Run the test with run</li>

   <li>If you set breakpoints: you can step line-by-line (including into function calls) with s or step over function calls with n</li>

   <li>If your code segfaults, you can run bt to see a stack trace</li>

  </ul></li>

</ol>

For more information on gdb, please see one of the many tutorials linked above.

To get an individual test name, you can look at the output produced by the tester. For example, the following failed test is test bst add left simple:

suites/bst_suite.c:38:F:test_bst_add_left_simple:test_bst_add_left_simple:0: Assertion failed… ^^^^^^^^^^^^^^^^^^^^

Beware that segfaulting tests will show the line number of the last test assertion made before the segfault, not the segfaulting line number itself. This is a limitation of the testing library we use. To see what line in your code (or in the tests) is segfaulting, follow the “To debug a specific test using gdb” instructions above.