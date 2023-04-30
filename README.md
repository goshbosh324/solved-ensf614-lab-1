Download Link: https://assignmentchef.com/product/solved-ensf614-lab-1
<br>
<strong>Objectives:</strong>

This lab assignments is designed to give you some experience with the process of developing, compiling, running a simple C program, and learning basic constructs of C programming such as:

<ul>

 <li>Using standard input/output library functions printf and scanf.</li>

 <li>Using C/C++ control structures and more importantly pointers.</li>

</ul>

<strong>Please heed these advices: </strong>

<ol>

 <li>Some exercises in this lab and future labs will not be marked. <strong>Please do not skip them</strong>, as unmarked exercises are as important as other exercises.</li>

 <li>Some students skip directly to the exercises that involve writing code, skipping the sections such as</li>

</ol>

“<strong>Read This First</strong>”, or postponing the diagram-drawing until later. That’s a bad idea for several reasons:

<ol>

 <li>“<strong>Read This First</strong>” sections normally explain some of technical or syntax details that may help you to solve the problem, or may provide you with some hints.</li>

 <li>Drawing diagrams is an important part of learning how to visualize memory used in C and C++ programs. If you do diagram-drawing exercises at the last minute, you won’t learn the material very well. If you do the diagrams first, you may find it easier to understand the code-writing exercises, so you may be able to finish them more quickly.</li>

</ol>

<strong>Important Notes: </strong>




<ul>

 <li>Some lab exercises may ask you to draw a diagram, and most of the students prefer to hand-draw them. In these cases, you need to <strong>scan</strong> your diagram with a scanner or an appropriate device such as your mobile phone and insert the scanned picture of your diagram into your PDF file. A possible mobile app to scan your documents is <strong>Microsoft Lens</strong> that you can install it on you mobile device for free. Please make sure your diagram is clear and readable, otherwise you may either lose marks, or it could be impossible for TAs to mark it at all. <strong>           </strong></li>

</ul>

<strong> </strong>

<strong>Exercise A: Creating a C source file, building and running an executable </strong>




<strong>Read This First: </strong>

If this is your first attempt to develop a C program, please do it so that you start to become comfortable with program development in C and particularly using your favorite development environment such as Visual Studio, Xcode, Geany, or smple editor such as Notepad++.  Before starting this exercise, please read the slides on “<strong>Getting Started</strong>”.




<strong>What to Do: </strong>

<ul>

 <li>Startup favorite editor or IDE.</li>

 <li>Into the editing area, type exactly in all the following C code:</li>

</ul>




<ul>

 <li>Now save your file as: c</li>

 <li>If you are using a text editor and Cygwin, or light IDEs such as Geany, on your operating system terminal navigate to your working directory (the same directory that you saved your c,then on the command line enter:</li>

</ul>




gcc -Wall lab1exe_A.c




If the command succeeds, an executable file called a.exe (or on a Mac computer, a.out) will have been created. If the command fails — which will be indicated by one or more error Messages–go back to your editor and fix the code, save the file again, try gcc  again.

<ul>

 <li>Once you have an executable, run it a few times by using the command</li>

</ul>

./a.exe (or ./a.out on a Mac machine)

over and over.




Try different inputs each time; see what happens if you enter letters or punctuation instead of numbers.




Hint:  You don’t need to type ‘./a.exe’ over and over! You can use the up arrow on your keyboard to retrieve previously entered commands.




Of course, if you are using more advanced IDEs such as Visual studio, you should use the features of those tools and you don’t need to enter gcc command or run the executables such as a.exe and a.out.




<strong> </strong>

<strong>Exercise B – Projectile Time and Distance Calculator </strong>

<strong>Read This First – A Brief Note on scanf Library Function </strong>

scanf is a Standard C Library function that can be used to read terminal input into variables. The first argument to scanf is a string constant with one or more format specifiers, like %d or %lf, and the remaining arguments are the addresses of the variables into which scanf will put the input data.

Here is the list of format specifiers for <strong>some</strong> of the simple C data types:

<table width="300">

 <tbody>

  <tr>

   <td width="120"><strong>C Data type </strong></td>

   <td width="180"><strong>Format Specifier </strong></td>

  </tr>

  <tr>

   <td width="120">int</td>

   <td width="180">%d</td>

  </tr>

  <tr>

   <td width="120">float</td>

   <td width="180">%f</td>

  </tr>

  <tr>

   <td width="120">double</td>

   <td width="180">%lf</td>

  </tr>

  <tr>

   <td width="120">char</td>

   <td width="180">%c</td>

  </tr>

  <tr>

   <td width="120">long int</td>

   <td width="180">%ld</td>

  </tr>

 </tbody>

</table>

For example, if <strong>x</strong> is a double data type, you can use the following syntax to put the input into <strong>x</strong>:

<strong>       </strong>int n;        double x;

printf(“Please enter the value of x: “);        n = scanf(“%lf”, &amp;x);

In this example, when scanf successfully reads a value for x, it returns 1. But In general, scanf returns the number of items that has read successfully.  And if it fails to read any number because of invalid user’s input, returns zero. For example, if user instead of a number enters a few letters such ‘abcd’ for x, scanf fails and the value of n will be zero. Also, in the following example if user enter two integer numbers for x and y, the value of n will 2.

int x, y, n;

printf(“Please enter the value of x: “);        n = scanf(“%d%d”, &amp;x, &amp;y);

<strong>Read This Second </strong>

In physics, assuming a flat Earth and no air resistance, a projectile launched with specific initial conditions will have a predictable range (maximum distance), and a predictable travel time.

The range or maximum horizontal distance traveled by the projectile can be approximately calculated by:




Where: <em>g is gravitation acceleration (</em>9.81 m/s<sup>2</sup> )

<em>θ</em>: the angle at which the projectile is launched in degrees <em>v</em>: the velocity at which the projectile is launched <em>d</em>: the total horizontal distance travelled by the projectile

To calulate the projectile travel time (t),  when reaches the maximum horizontal distace the followig formaula can be used :

<strong> </strong>

In this exercise you will complete a given C source file called lab1exe_B.c that prompt the user to enter a projectile’s initial launch velocity (n), and displays the table of maximum horizontal distance and travel time for the trajectory angles of 0 to 90 degrees.

<strong>What to Do:</strong> <strong> </strong>

First, download file lab1exe_B.c from D2L. In this file the definition of function main and the function prototypes for four other functions are given. Your job is to complete the definition of missing functions as follows:

<strong>Function create_table:</strong> which is called by the main function, receives the projectile initial velocity and displays a table of projectile’s maximum travel distance (d) and time (t), for trajectory angles of 0 to 90 (degrees), with increments of 5 degrees. Here is the sample of the required table:




Angle          t            d

(deg)        (sec)         (m)

0.000000     0.000000     0.000000

5.000000     1.778689     177.192018

10.000000    3.543840     349.000146




You don’t have to worry about the format or the number of digits after the decimal point. The default format is acceptable.

<strong>Function projectile_travel_time:</strong> receives two double arguments, the trajectory angle (q), and the initial velocity (n) and returns projectile travel time (t).

<strong>Function projectile_travel_distance:</strong> receives two double arguments, the trajectory angle (q), and the initial velocity (n) and returns projectile maximum horizontal distance (d).

<strong>Function degree_to_radian: </strong>receives an angle in degrees and converts to radian.  This function is needed, because C library function sin needs its argument value to be in radian.

Notes:

<ul>

 <li>To use C library function sin, you need to include header file h. And, if you are compiling and running the program from command line use –lm option to link the math library:</li>

</ul>

gcc -Wall –lm lab1exe_C.c

<ul>

 <li>Please pay attention for constant values of p, and gravitation acceleration, g, the following lines are already included in the given file. using preprocess or #define is another way of indicating constants in C:</li>

</ul>

#define PI 3.141592654

#define G 9.8

As an example anywhere in the code that compiler finds the word PI it will be replaced with

3.141592654.

<strong> </strong>

<strong>What to Submit: </strong>

Submit the copy of your program (your code and the program output) as part of your lab report in PDF format. You don’t need to upload your actual source code (the .c file). Only it must be copied and pasted into your lab report along with the program’s output.

<strong> </strong>

<strong>Exercise C – Introduction to Pointers </strong>

This exercise will not be marked, and you shouldn’t submit anything.

<strong>Read This First </strong>

This is an important exercise in ENSF 619<em>.</em> If you don’t become comfortable with pointers, you will not be able to work with C. Spend as much time on this exercise as is necessary to understand exactly what is happening at every step in the given program.

<strong>What to do </strong>

Download the file lab1exe_C.c . Trace through the execution of the program to determine what the output will be. Now assume the following addresses for variables:

sam   9880   fred  9884   bar   9888   foo   9892




Draw a set of AR diagrams for points two through five and <strong><u>use the given address numbers as values of the</u> <u>pointers (don’t use arrow notation in this exercise)</u></strong>. To understand how to draw these diagrams the solution for point one is given in the following figure:




After you completed the exercise, compile lab1exe_C.c and check your predicted output against the actual program output.

<strong>Exercise D: Pointers as function arguments </strong>

<h1>What to do – Part I</h1>

First copy the file lab1exe_D1.c from D2L. Carefully make diagrams for point one in this programs using “<strong>Arrow Notation</strong>” as is discussed in the set of slides called 03_Activation Records on the D2L, then compare your solution with the posted solution on the D2L.

<strong> </strong>

<strong>Exercise D: Pointers as function arguments </strong>

<strong>What to do – Part I </strong>

First copy the file lab1exe_D1.c from D2L. Carefully make diagrams for point one in this programs using “<strong>Arrow Notation</strong>” as we discussed during lectures (you don’t need to use made-up addresses, the way that we did it in the previous exercise). Then compare your solution with the posted solution on the D2L.




<em>There is nothing to submit for this part </em>




<strong>What to do – Part</strong> II




Now download the file lab1exe_D2.c from D2L and draw AR diagram for point one in this file.




<strong><em>Submit the AR diagram for part II as part of your lab report.</em></strong>

<strong> </strong>

<strong> </strong>

<strong>Exercise E: Using pointers to get a function to change variables </strong>

<h1>Read This First</h1>

Here is an important note about terminology:

<ul>

 <li><em>Don’t</em> say, “Pointers can be used to make a function return more than one value.” A function can never have more than one return value. A return value is transmitted by a return statement, not by a pointer.</li>

 <li><em>Do</em> say, “Pointer arguments can be used to simulate call by reference,” or, “Functions with pointer arguments can have the side effect of modifying the variables that the pointer arguments point to.”</li>

</ul>

<h1>What to do</h1>

Make a copy of the file lab1exe_E.c from D2L.  If you try to compile and run this program it will give you some warning because the definition of function time_convert is missing.




Write the function definition for time_convert and add code to the main function to call time_convert before it prints answers.




<strong> </strong>