Download Link: https://assignmentchef.com/product/solved-cse102-homework-8
<br>
<ul>

 <li>Your program reads two files:

  <ul>

   <li>txt</li>

   <li>txt</li>

  </ul></li>

 <li>According to content in <sub>txt</sub>, the program <strong><sub>dynamically </sub></strong>creates a directory structure and evaluates the commands listed in <sub>commands.txt</sub>.</li>

 <li>Your program prints the list of files and directories with their full addresses to a file called <sub>txt</sub>. <strong>files.txt</strong></li>

 <li>Each line is a file or directory name. This file lists all the necessary information for you to create a full directory structure. There won’t be any errors but the order can be arbitrary. You have to figure out the root directory and the rest of the hierarchy from this file. For this initial file, you can assume all the directory names will be unique. You can read the file line by line and create independent structures for each line, then you can combine all the created structures in order to create the final structure. Assume, there isn’t any empty directory. Each line ends with a file name.</li>

 <li>Example:</li>

 <li>Below is the contents of a <sub>txt </sub>file:</li>

</ul>

directory1/directory2/file1 directory2/file3 directory0/directory1/file5 directory0/file4

<ul>

 <li>For this example, the structure is as follows:</li>

</ul>

directory0 directory1 directory2 file1 file3

file5

file4

<h1>commands.txt</h1>

This file includes several commands which work on the directory structure you read from <sub>files.txt</sub>. Each line is a command. The following should be recognized:

copy A B move A B delete A cd A <strong>copy A B</strong>

This command has two operants: <sub>A </sub>and <sub>B</sub>. <sub>B </sub>is a directory. <sub>A </sub>can be a directory or a file. This command copies

A and places it under directory <sub>B</sub>. If <sub>A </sub>is a directory, all the structure under <sub>A </sub>is copied under <sub>B</sub>. <sub>A </sub>and <sub>B </sub>can be provided as full directory or relative directory.

<h2>move A B</h2>

Similar to <sub>copy A B</sub>. This moves <sub>A </sub>under <sub>B </sub>and deletes the original copy of <sub>A </sub><strong>delete A</strong>

Removes <sub>A </sub>from the structure.

<h2>cd A</h2>

This command changes the current directory to <sub>A</sub>. <sub>A </sub>is definitely a directory not a file. There are special replacements for <sub>A</sub>:

<ul>

 <li><sub>.. </sub>: changes the current director to the parent directory.(If there is no parent, current directory does not change)</li>

 <li><sub>/ </sub>: changes the current directory to root. Root directory is the top directory. There isn’t a parent directory above the root directory.</li>

</ul>

<strong>Example:</strong>

Assume that your program reads the example <sub>files.txt </sub>given above. Current directory is the top(root) directory which is directory0

<ul>

 <li>Issuing the command copy /directory0/directory1/directory2/file1 /directory0, copies file1 and places it under <sub>directory0</sub>. Following is the result of this command:</li>

</ul>

directory0 directory1 directory2 file1 file3

file5 file1 file4

<ul>

 <li>similarly, the command copy file4 directory1 copies file4 to the directory directory1. Here, current directory is <sub>directory0 </sub>so, <sub>file4 </sub>and <sub>directory1 </sub>are given as relative addresses. After this command, the structure changes to the following version:</li>

</ul>

directory0 directory1 directory2 file1 file3

file4 file5 file1 file4

<ul>

 <li>If there is a command <sub>delete directory1</sub>, it will change the structure as follows:</li>

</ul>

directory0 file1 file4

<h1>output.txt</h1>

This file lists all the files and directories with their full addresses. If your directory structure is as follows:

directory0 directory1 directory2 file1 file3 file4 file5 file1 file4

You should create the following <sub>output.txt </sub>file:

directory0 directory0/directory1 directory0/file1 directory0/file4 directory0/directory1/directory2 directory0/directory1/file4 directory0/directory1/file5 directory0/directory1/directory2/file1 directory0/directory1/directory2/file4

<ul>

 <li>The order is not important.</li>

</ul>

<h1>Remarks</h1>

<ul>

 <li>This assignment is about using linked lists. You should use structures and/or unions.</li>

 <li>You need to keep the track of <sub>current directory </sub>and issue the commands.</li>

 <li>You can assume that all the files and directories under the same parent directory will have different(unique if in the same directory) names.</li>

 <li>Do not submit your code without testing it with several different scenarios.</li>

 <li>Write comments in your code.</li>

 <li>Do not submit any of the files you used for testing.</li>

 <li>Do not submit your output file.</li>

</ul>

<strong>Turn in:</strong>

<ul>

 <li>Source code of a complete C program. Name of the file should be in this format: <sub>&lt;full_name&gt;_&lt;id&gt;.c</sub>.</li>

 <li>Example: <sub>c</sub>. Please do not use any Turkish special characters.</li>

 <li>You don’t need to use an IDE for this assignment. Your code will be compiled and run in a command window.</li>

 <li>Your code will be compiled and tested on a Linux machine(Ubuntu). GCC will be used.</li>

 <li>Make sure you don’t get compile errors when you issue this command : <sub>gcc &lt;full_name&gt;_&lt;id&gt;.c</sub>.</li>

 <li>A script will be used in order to check the correctness of your results. So, be careful not to violate the expected output format.</li>

 <li>Provide comments unless you are not interested in partial credit. (If I cannot easily understand your design, you may loose points.)</li>

</ul>

You may not get full credit if your implementation contradicts with the statements in this document.