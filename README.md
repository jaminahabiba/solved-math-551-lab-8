Download Link: https://assignmentchef.com/product/solved-math-551-lab-8
<br>
<strong>Goal: </strong>In this assignment, you will use Matlab to visualize the action of a 2×2 matrix <strong>A</strong>. You will practice thinking of <strong>A </strong>as a type of abstract system that takes as input a 2-vector <strong>x </strong>and produces as output another 2vector <strong>Ax </strong>(the matrix-vector product). Using a common engineering style for representing abstract systems, <strong>A </strong>can be represented as follows.

<h1>x    Ax</h1>

With this way of thinking about <strong>A</strong>, the task of solving a linear system <strong>Ax </strong>= <strong>b </strong>can be rephrased as a design problem: Find the input <strong>x </strong>to give to <strong>A </strong>in order to achieve the desired output <strong>b</strong>.

<h1>?b</h1>

Learning this way of thinking of matrices can be amazingly valuable in the remainder of Math 551, as well as in a large number of other courses in math, engineering and the sciences.

<strong>Getting started: </strong>You will need to download three files and place them into your working directory:

<ul>

 <li>m: the M-file you will edit during the lab</li>

 <li>draw coords.m: a function for drawing coordinate systems</li>

 <li>draw vec.m: a function for drawing vectors</li>

</ul>

<strong>What you have to submit: </strong>The file m551lab08.m, which you will modify during the lab session.

<strong>Reminders About the Grading Software</strong>

Remember, the labs are graded with the help of software tools. If you do not follow the instructions, you will lose points. If the instructions ask you to assign a value to a variable, you must <strong>use the variable name given in the instructions</strong>. If the instructions ask you to make a variable named x1 and instead you make a variable named x or X or X1 or any name other than x1, the grading software will not find your variable and you <em>will </em>lose points. Required variables are listed in the lab instructions in a gray box like this:

<h2>Variables: x1, A, q</h2>

At times you will also be asked to answer questions in a comment in your M-file. You must <strong>format your text answers correctly</strong>. Questions that you must answer are shown in gray boxes in the lab. For example, if you see the instruction

Q7: What does the Matlab command lu do? your file must contain a line similar to the following somewhere

% Q7: It computes the LU decomposition of a matrix.

The important points about the formatting are

<ul>

 <li>The answer is on a single line.</li>

 <li>The first characters on the line is the comment character %.</li>

 <li>The answer is labeled in the form Q<em>n</em>:, where <em>n </em>stands for the question number from the gray box.</li>

</ul>

If you do not format your answers correctly, the grading software will not find them and you <em>will </em>lose points.

<strong>Tasks</strong>

<ol>

 <li>Open the file m in the Matlab editor. Move to the cell titled “Part 1” and run it. Matlab should open a figure window that looks like the following.</li>

</ol>

-6             -4             -2              0              2              4              6                            -6             -4             -2              0              2              4              6

Spend some time getting to know this figure. On the left, you see a representation of some vectors in R<sup>2</sup>. The red and blue vectors are the vectors

<strong>e</strong>         and         <strong>e</strong>

respectively. These two vectors define a very natural grid in the plane made up of two types of lines (shown in gray). First, there are lines that run parallel to the blue vector and are spaced apart by a length determined by the red vector. Second, there are lines that run parallel to the red vector and are spaced apart by a length determined by the blue vector. These lines intersect at points of the form <em>k</em><strong>e</strong><sub>1 </sub>+ <em>`</em><strong>e</strong><sub>2 </sub>where <em>k </em>and <em>` </em>are both integers. By looking at the grid lines, you can see that the magenta vector is <strong>x </strong>= <strong>e</strong><sub>1 </sub>+ 3<strong>e</strong><sub>2</sub>.

Now, look at the plot on the right. Understanding this plot will help you visualize the behavior of the matrix

<strong>A </strong><em>.</em>

First, spend some time convincing yourself that the red and blue vectors on the right are exactly <strong>Ae</strong><sub>1 </sub>and <strong>Ae</strong><sub>2</sub>. Next, take a look at the thin gray lines. Although they are no longer horizontal and vertical, these lines still have the interpretation from before. There are lines parallel to red spaced by blue, and lines parallel to blue spaced by red. Think of the lines as city streets. In the left plot, the endpoint of the magenta vector <strong>x </strong>can be located by following the directions “Go one block in the red direction and three blocks in the blue direction.” And in the right plot, the magenta vector <strong>Ax </strong>can be described in exactly the same way! This is a geometric way of visualizing the fact that

<strong>Ax </strong>= <strong>A</strong>(1<strong>e</strong><sub>1 </sub>+ 3<strong>e</strong><sub>2</sub>) = 1(<strong>Ae</strong><sub>1</sub>) + 3(<strong>Ae</strong><sub>2</sub>)<em>.</em>

<ol start="2">

 <li>Now, you’ll use these ideas to solve a linear system. Notice that there is a gray vector drawn in the right plot of the figure above. This is your target vector <strong>b </strong>defined in the M-file as</li>

</ol>

% define the target vector b = [ 2.5; 1 ];

Your task is to change the definition of x part1 at the top of the cell until the magenta vector is identical to the gray vector. You can do this by trial and error, but you’ll be much more efficient if you spend a little time counting the “city blocks”. As a hint, notice that you need to go in the opposite direction of the blue vector, but in the same direction as the red. So your blue component should be negative and your red component positive.

When you run the cell, notice that the script produces some output in the command window. With the original value of x part1, the output is

Part 1: error in Ax-b = 7.500000e+00

You’ll know that you’re finished when you get the error to 0. (Yes, in this case, you can actually get

0 error.)

<h2>Variables: x part1</h2>

<ol start="3">

 <li>Now move to the cell labeled “Part 2” and run it. This cell behaves very much like the previous, except for two changes. First, I have changed the definition of <strong>A </strong>to</li>

</ol>

<strong>A </strong><em> .</em>

Second, I have added another vector (green) to the plots. Now, Matlab produces a figure that looks like the following.

-6             -4             -2              0              2              4              6                            -6             -4             -2              0              2              4              6

To convince yourself that the the plot makes sense, you should verify that the vectors <strong>Ae</strong><sub>1 </sub>and <strong>Ae</strong><sub>2 </sub>both lie on the same line through the origin. That means that the “streets” in the blue direction are exactly the same as those in the red direction. In fact, there’s only one street in the transformed city.

Note that, again, the target vector <strong>b </strong>is drawn in gray. Locate the appropriate place at the very top of the M-file cell and answer the following question.

Q1: Why can’t there exist a solution to the system <strong>Ax </strong>= <strong>b </strong>in this case?

<ol start="4">

 <li>Now, let’s figure out a system we <em>can </em> Near the top of the cell, locate the definition of the variable b part2. Change this definition so that

  <ul>

   <li>a solution does exist, and</li>

   <li>the first component of <strong>b </strong>is 2.</li>

  </ul></li>

</ol>

Again, you can probably find the right vector by trial and error, but it might pay to think for a bit about what line <strong>b </strong>lies on.

Once you have found the right-hand side <strong>b</strong>, move a few lines up in the M-file to where x1 part2 and x2 part2 are defined. These lines define vectors <strong>x</strong><sub>1 </sub>and <strong>x</strong><sub>2 </sub>(magenta and green, respectively). Your next task is to modify their definitions so that

<ul>

 <li>both are solutions to the linear system with your new <strong>b</strong>,</li>

 <li>the second component of <strong>x</strong><sub>1 </sub>is 0, and (c) the first component of <strong>x</strong><sub>2 </sub>is 0.</li>

</ul>

The code in the cell will provide feedback on your progress. You’ll know you’re finished when no warnings are reported and when both errors are exactly 0.

Variables: b part2, x1 part2, x2 part2

<ol start="5">

 <li>In the final part of this lab, let’s return to the original matrix <strong>A </strong>and ask a different question. Move to “Part 3” in the M-file and run the cell. Matlab should produce the following figure.</li>

</ol>

-6             -4             -2              0              2              4              6                            -6             -4             -2             0              2              4              6

We’re basically back to where we started in Part 1, but now, instead of a fixed <strong>b</strong>, we’re going to have a moving target. More specifically, the magenta vector in the left plot is a vector <strong>x </strong>defined in the variable x part3, and the magenta vector on the right is <strong>Ax</strong>. However, this time the gray vector on the right is simply <strong>x </strong>again. Your task is to find a vector <strong>x </strong>so that, on the right, the gray vector (<strong>x</strong>) and the magenta vector (<strong>Ax</strong>) lie on the same line. (Such a vector is called an <em>eigenvector </em>of <strong>A</strong>.) To see that such a thing is possible, find the following code in this cell.

% define the vector x x_part3 = [ 1; 1 ]; % first figure

%x_part3 = [ 0.732050807568877; 2.0 ]; % second figure

Switch the comment character (%) from the last line to the one above, so that the code looks like this.

% define the vector x

%x_part3 = [ 1; 1 ]; % first figure

x_part3 = [ 0.732050807568877; 2.0 ]; % second figure Run the cell again and Matlab should produce the following picture.

-6             -4             -2              0              2              4              6                            -6             -4             -2             0              2              4              6

Although it might not be easy to tell for sure just by looking at the plot, the gray and magenta vectors√

do lie on the same line. In fact, <strong>Ax </strong>= − 3<strong>x</strong>. To check this, enter the following into Matlab’s command window.

&gt;&gt; A*x_part3 + sqrt(3)*x_part3 ans =

1.0e-15 *

-0.8882

0.4441

√

This shows that the difference between <strong>Ax </strong>and − 3<strong>x </strong>is <strong>0 </strong>plus some roundoff errors.

√

Your final task in this lab is to find another eigenvector of <strong>A</strong>, this time with <strong>Ax </strong>= + 3<strong>x</strong>. The particular <strong>x </strong>you are seeking has 2 as its second component and points into the second quadrant (the first component is negative). If you’ve learned about eigenvalues already, you may know how to find this vector using Matlab functions. If not, or if you’re interested in developing your geometric intuition, use trial and error. Since you know that the second component should be 2 and the first component should be negative, it won’t take too long. You’ll know you’re finished when the code produces no warnings and when your error is less than 10<sup>−2</sup>. Using only 3 digits for <strong>x</strong>:

x_part3 = [ -?.??; 2 ];

I was able to get the output to look like this:

************************************************************

* Part 3

************************************************************ error in current guess = 4.367738e-03

************************************************************

(If you want more of a challenge, try to get the error below 10<sup>−3</sup>. I got an error just below that using

5 digits.)

<h2>Variables: x part3</h2>