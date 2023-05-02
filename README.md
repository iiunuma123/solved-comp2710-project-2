Download Link: https://assignmentchef.com/product/solved-comp2710-project-2
<br>
<span class="kksr-muted">Rate this product</span>

Goals:

<ul>

 <li>To learn “while” and “do-while” statements</li>

 <li>To learn how to define functions</li>

 <li>To write a test driver</li>

 <li>To learn how to use assert()</li>

 <li>To use random numbers Description:In the land of Puzzlevania, Aaron, Bob, and Charlie had an argument over which one of them was the greatest puzzle-solver of all time. To end the argument once and for all, they agreed on a duel to the death (this makes sense?). Aaron was a poor shooter and only hit this target with a probability of 1/3. Bob was a bit better and hit his target with a probability of 1/2. Charlie was an expert marksman and never missed. A hit means a kill and the person hit drops out of the duel.To compensate for the inequities in their marksmanship skills, the three decided that they would fire in turns, starting with Aaron, followed by Bob, and then by Charlie. The cycle would repeat until there was one man standing. That man would be remembered for all time as the Greatest Puzzle-Solver of All Time.An obvious and reasonable strategy is for each man to shoot at the most accurate shooter still alive, on the grounds that this shooter is the deadliest and has the best chance of hitting back.Write a program to simulate the duel using this strategy. Your program should use random numbers and the probabilities given in the problem to determine whether a shooter hits his target. You will likely want to create multiple functions to complete the problem. My solution had only one function to simulate the duels and it passed in the odds and the three guys as pass-by-reference parameters. Once you can simulate a duel, add a loop to your program that simulates 10,000 duels. Count the number of times that each contestant wins and print the probability of winning for each contestant (e.g., for Aaron your might output “Aaron won 3612/10000 duels or 36.12%).Strategy 2: An alternative strategy for Aaron is to intentionally miss on his first shot. Write a function to simulate Strategy 2. Your program will determine which strategy is better for Aaron.</li>

</ul>

1

Note: You must provide the following user interface. Red text might be different for different runs due to the random number. You do not need to display text in red. Please replace “Li” with your name.

*** Welcome to Li’s Duel Simulator ***Unit Testing 1: Function – at_least_two_alive()

Case 1: Aaron alive, Bob alive, Charlie alive Case passed …Case 2: Aaron dead, Bob alive, Charlie alive Case passed …

Case 3: Aaron alive, Bob dead, Charlie alive Case passed …Case 4: Aaron alive, Bob alive, Charlie dead Case passed …

Case 5: Aaron dead, Bob dead, Charlie alive Case passed …Case 6: Aaron dead, Bob alive, Charlie dead Case passed …

Case 7: Aaron alive, Bob dead, Charlie dead Case passed …Case 8: Aaron dead, Bob dead, Charlie dead Case passed …

Press any key to continue…

Unit Testing 2: Function Aaron_shoots1(Bob_alive, Charlie_alive) Case 1: Bob alive, Charlie alive

Aaron is shooting at Charlie Case 2: Bob dead, Charlie alive

Aaron is shooting at Charlie Case 3: Bob alive, Charlie dead

Aaron is shooting at Bob Press any key to continue…

Unit Testing 3: Function Bob_shoots(Aaron_alive, Charlie_alive) Case 1: Aaron alive, Charlie alive

Bob is shooting at Charlie Case 2: Aaron dead, Charlie alive

Bob is shooting at Charlie Case 3: Aaron alive, Charlie dead Bob is shooting at Aaron

Press any key to continue…

Unit Testing 4: Function Charlie_shoots(Aaron_alive, Bob_alive) Case 1: Aaron alive, Bob alive

Charlie is shooting at Bob Case 2: Aaron dead, Bob alive

Charlie is shooting at Bob Case 3: Aaron alive, Bob dead

Charlie is shooting at Aaron Press any key to continue…

2

Unit Testing 5: Function Aaron_shoots2(Bob_alive, Charlie_alive) Case 1: Bob alive, Charlie alive

Aaron intentionally misses his first shot

Both Bob and Charlie are alive. Case 2: Bob dead, Charlie alive

Aaron is shooting at Charlie Case 3: Bob alive, Charlie dead

Aaron is shooting at Bob Press any key to continue…

Ready to test strategy 1 (run 10000 times): Press any key to continue…

Aaron won 3565/10000 duels or 35.65% Bob won 4226/10000 duels or 42.26% Charlie won 2209/10000 duels or 22.09%

Ready to test strategy 2 (run 10000 times): Press any key to continue…

Aaron won 4216/10000 duels or 42.16% Bob won 2465/10000 duels or 24.65% Charlie won 3319/10000 duels or 33.19%

Strategy 2 is better than strategy 1.

Requirements:

<ol>

 <li>You must follow the above user interface to implement your program.</li>

 <li>You must implement the following functions:</li>

</ol>

1) bool at_least_two_alive(bool A_alive, bool B_alive, C_alive)

/* /* /* /* /*

Input: A_alive indicates whether Aaron is alive */ B_alive indicates whether Bob is alive */ C_alive indicates whether Charlie is alive */

Return: true if at least two are alive */ otherwise return false */

2) void Aaron_shoots1(bool&amp; B_alive, bool&amp; C_alive)

/* * * * * */

Strategy 1: Use call by referenceInput: B_alive indicates whether Bob alive or dead

C_alive indicates whether Charlie is alive or dead Return: Change B_alive into false if Bob is killed.

Change C_alive into false if Charlie is killed.

3

3) void Bob_shoots(bool&amp; A_alive, bool&amp; C_alive)

/* * * * * */

/* * * * * */

/* * * * * */

Call by referenceInput: A_alive indicates if Aaron is alive or dead

C_alive indicates whether Charlie is alive or dead Return: Change A_alive into false if Aaron is killed.

Change C_alive into false if Charlie is killed. 4) void Charlie_shoots(bool&amp; A_alive, bool&amp; B_alive)

Call by referenceInput: A_alive indicates if Aaron is alive or dead

B_alive indicates whether Bob is alive or dead Return: Change A_alive into false if Aaron is killed.

Change B_alive into false if Bob is killed. 5) void Aaron_shoots2(bool&amp; B_alive, bool&amp; C_alive)

Strategy 2: Use call by referenceInput: B_alive indicates whether Bob alive or dead

C_alive indicates whether Charlie is alive or dead Return: Change B_alive into false if Bob is killed.

Change C_alive into false if Charlie is killed.

<ol start="2">

 <li>You must implement five unit test drivers (five functions) to test the above five functions (see the example output on pages 2 and 3).</li>

 <li>You must use assert in your test driver.</li>

 <li>You must define at least three constants in your implementation. For example,the total number of runs (i.e., 10,000) can be defined as a constant.</li>

</ol>

Hints:

<ol>

 <li>How to implement “Press any Enter to continue…” cout &lt;&lt; “Press Enter to continue…”;cin.ignore().get(); //Pause Command for Linux TerminalNote: you can implement the above two lines as a function to be repeatedly called by other functions in your program.</li>

 <li>You may need to use the following libraries.# include &lt;iostream&gt; # include &lt;stdlib.h&gt; # include &lt;assert.h&gt; # include &lt;ctime&gt;</li>

 <li>Initialize your random number generator as below:srand(time(0));</li>

</ol>

4

4. A sample code of generating a random number is given below:

/* Assume that the probabilty of hit a target is 25 percent */ int shoot_target_result;

shoot_target_result = rand()%100;

if (shoot_target_result &lt;= 25) { cout&lt;&lt;“Hit the target
”;

/* add more code here */ }

5. Please follow the following sample test driver to implement the test driver.

void test_at_least_two_alive(void) {cout &lt;&lt; “Unit Testing 1: Function – at_least_two_alive()
”;

cout &lt;&lt; “Case 1: Aaron alive, Bob alive, Charlie alive
”; assert(true == at_least_two_alive(true, true, true));cout &lt;&lt; “Case passed …
”;

cout &lt;&lt; “Case 2: Aaron dead, Bob alive, Charlie alive
”; assert(true == at_least_two_alive(false, true, true)); cout &lt;&lt; “Case passed …
”;

cout &lt;&lt; “Case 3: Aaron alive, Bob dead, Charlie alive
”; assert(true == at_least_two_alive(true, false, true)); cout &lt;&lt; “Case passed …
”;

/* add test cases 4-6 below */

… }

<ol start="6">

 <li>If your strategy 1 is better than your strategy 2, then please check your source code. In this case, it is likely that you have incorrectly implemented strategy 2. Please ensure that strategy 2 is better than strategy 1.</li>

 <li>The framework of the source code is given below:</li>

</ol>

# include &lt;iostream&gt; # include &lt;stdlib.h&gt; # include &lt;assert.h&gt; # include &lt;ctime&gt; using namespace std;

//prototypesbool at_least_two_alive(bool A_alive, bool B_alive, bool C_alive); /* Input: A_alive indicates whether Aaron is alive */

<ul>

 <li>/*  B_alive indicates whether Bob is alive */</li>

 <li>/*  C_alive indicates whether Charlie is alive */</li>

</ul>

5

/* /*

/* *

*/

void test_at_least_two_alive(void);/* This is a test driver for at_least_two_alive() */

/** Add more prototypes for other test drivers below */

int main() {

/** This is the main function *…*/

}

/* Implementation of at_least_two_alive() */bool at_least_two_alive(bool A_alive, bool B_alive, bool C_alive) {

/* add the implementation below */ }

/* Implementation of the test driver for at_least_two_alive() */ void test_at_least_two_alive(void) {

cout &lt;&lt; “Unit Testing 1: Function – at_least_two_alive()
”;

cout &lt;&lt; “Case 1: Aaron alive, Bob alive, Charlie alive
”; assert(true == at_least_two_alive(true, true, true));cout &lt;&lt; “Case passed …
”;

cout &lt;&lt; “Case 2: Aaron dead, Bob alive, Charlie alive
”; assert(true == at_least_two_alive(false, true, true)); cout &lt;&lt; “Case passed …
”;

/* add test cases 4-6 below */ }

Return: true if at least two are alive */ otherwise return false */

Add other function prototypes below

Programming Environment:

Write a program in C++. Compile and run it using AU server (no matter what kind of text editor you use, please make sure your code could run on AU server, the only test bed we accept is AU server).

6

Grading:

<ol>

 <li>(5 points) Use comments to provide a heading at the top of your code containing your name, Auburn UserID, filename, and how to compile your code. Also describe any help or sources that you used (as per the syllabus).</li>

 <li>(5 points) Your source code file should be named as “project2_AUuserID.cpp”. Note: You will not lose any point, if Canvas automatically changes your file name (e.g., project2_abc0001-2.cpp) due to your resubmissions.</li>

 <li>(10 points) You must follow the specified user interface/example output.</li>

 <li>(5 points) Defined at least three constants.</li>

 <li>Implement five functions.</li>

 <li>Implement five test drivers for the functions.</li>

 <li>You must use assert() in your test drivers.</li>

 <li> Your program must compare strategy 1 with strategy 2.</li>

 <li> Quality of your source code.</li>

</ol>

Note: You will lose at least 40 points if there are compilation errors or warning messages when we compile your source code. You will lose points if you don’t use the specific program file name, or don’t have comments, or don’t have a comment block on EVERY program you hand in.

Deliverables: