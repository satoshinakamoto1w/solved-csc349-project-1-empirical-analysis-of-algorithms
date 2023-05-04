Download Link: https://assignmentchef.com/product/solved-csc349-project-1-empirical-analysis-of-algorithms
<br>



<ol>

 <li>Review algorithms learned in previous courses: selection sort, bubble sort, mergesort, quicksort.</li>

 <li>Implement algorithms constructed by different strategies, using different techniques. Selection and bubble sorts are iterative algorithms while mergesort and quicksort both are recursive algorithms representing two great examples of divide-and-conquer strategy.</li>

 <li>Analyze performance of implemented algorithms empirically, observing differences of their performances: selection and bubble sorts are O(N<sup>2</sup>) algorithms while mergesort and quicksort are O(NlogN) algorithms<sup>1</sup>. You will evaluate their performance based on their running time.</li>

</ol>

———–

<sup>1</sup>   <strong>Reminder</strong>: quicksort’s worst case takes O(N<sup>2</sup>) time. However, with some effort the worst case is made exponentially unlikely which means that quicksort’s expected performance is as in its average case and thus it is classified as O(NlogN) algorithm.

<strong> </strong>

<strong><u>PART 1</u></strong><strong>:  </strong><strong>I. Design and implement a class named <em>Sorts</em></strong>

<strong><em> </em></strong>

The <em>Sorts</em> class contains the implementation of <strong>4 sorting algorithms </strong>and<strong> NOTHING else</strong> (the implementation of these algorithms must be <strong>consistent</strong> with the posted <a href="http://users.csc.calpoly.edu/%7Ehghariby/SortingAlgorithms.pdf">handout</a><a href="http://users.csc.calpoly.edu/%7Ehghariby/SortingAlgorithms.pdf">)</a>. This class does NOT have any instance or class variables, any constants (public or private), or any <em>public </em>methods except the ones stated below. <em>Sorts</em> class contains only <strong>four <em>public</em> methods </strong>for the four sorting routines<strong> plus</strong> all necessary <strong><em>private</em></strong> methods that support them. The four public methods are:

<strong> </strong>

<em>      public static  void  selectionSort (int[] arr, int N)</em>

//Sorts the list of <em>N</em> elements contained in <em>arr[0..N-1]</em> using the <strong><em>selection sort</em></strong> algorithm.




<em>      public static  void  bubbleSort (int[] arr, int N)</em>

//Sorts the list of <em>N</em> elements contained in <em>arr[0..N-1]</em> using the <strong>improved</strong> <strong><em>bubble sort</em></strong> algorithm                  //(see the <a href="http://users.csc.calpoly.edu/%7Ehghariby/SortingAlgorithms.pdf">handout</a><a href="http://users.csc.calpoly.edu/%7Ehghariby/SortingAlgorithms.pdf">)</a>.




<em>      public static void mergeSort (int[] arr, int N)   </em>

//Sorts the list of <em>N</em> elements contained in <em>arr[0..N-1]</em> using the <strong><em>merge sort</em></strong> algorithm.




<em>      public static void quickSort (int[] arr, int N)   </em>

//Sorts the list of <em>N </em>elements contained in <em>arr[0..N-1]</em> using the <strong><em>quick sort</em> </strong>algorithm <strong>with  </strong>                 //<strong>median-of-three pivot <u>and</u> rearrangement of the three elements </strong>(see the <a href="http://users.csc.calpoly.edu/%7Ehghariby/SortingAlgorithms.pdf">handout</a><a href="http://users.csc.calpoly.edu/%7Ehghariby/SortingAlgorithms.pdf">)</a><strong>.</strong>







<strong><u>Notes</u>: </strong>1. The list given as a parameter may not fill the <em>arr</em> array: it occupies <em>arr’s </em>0 to<em> N-1 </em>cells.

<ol start="2">

 <li>No need for validity check – you can assume that <em>arr.length</em> &gt;0 and <em>N</em> &lt;= <em>arr.lenght</em>.</li>

</ol>




<strong><u>Attention</u>: </strong>you may <strong>NOT</strong> change the names or signatures of specified four <strong><u>public</u></strong> methods; <strong>BE CAREFUL</strong> about the upper/lowercase letters in method names (misspelled name will make the grading program fail). <u>You can define </u><em><u>private</u></em><u> methods as you see fit.</u>

<ol>

 <li><strong>Design and implement an application class (or classes) to test your 4 sorting methods and make sure they work correctly. Run <em>a lot of tests</em> for each sort. </strong></li>

</ol>

<strong> </strong>

<strong><u>Attention</u></strong><strong>: </strong>Do <strong>NOT</strong> submit this application class (or classes) – it only serves as a testing tool for <em>you</em>. <strong> </strong><strong>The grader will run his own driver to test your methods.</strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong><u>PART 2:</u></strong> <strong>Design and implement an application class named <em>SortTimes </em>to generate the running times of <em>Sorts </em>class’ 4 routines. </strong>




This class only needs a <em>main </em>method designed to run <em>Sorts</em> class’ public methods multiple times for different size lists and <strong>output the execution time</strong> in <strong><u>milliseconds</u></strong> for each method in each run.

<strong><u>Attention:</u></strong>  1. To get the execution time of a method, you can capture the system time immediately before and immediately after the method call, and then take the difference.

<ol start="2">

 <li>To obtain the <strong>system time</strong>, for more accuracy, use <em>System </em>class’ <em>static</em> method <em>nanoTime() </em>which returns the system time in nanoseconds as a <strong><em>long </em></strong>type value. To obtain the running time in <strong>milliseconds</strong>, you need to <strong>divide the obtained running time by 1,000,000</strong>. <u>Note</u>: time values should be represented as <strong><u>integer numbers.</u></strong></li>

</ol>




Here is the description of steps that need to be done in <em>main</em> (variable N represents the number of elements in the list).




<ul>

 <li>Define 4 arrays for <strong>160,000</strong> <strong><em>int</em></strong> type elements (the <strong>max</strong> size list you need to sort is 160,000). <u>Notes</u>: You<strong> need 4 copies</strong> of the original list: a sorting method alters the original list (sorts it), therefore you cannot use it as an input list for another method, hence the need for 4 copies of the original list. To hold 4 copies of the list, you need 4 arrays so you can pass different copies/arrays to different sorting methods.</li>

</ul>

<ol start="2">

 <li>To test an algorithm on different size lists, <u>it’s more efficient to have <strong>one</strong> array of <strong>max</strong> size</u> (and fill it partially) rather than using a different N-size array for each N.</li>

</ol>




<ul>

 <li><strong>For different values of N</strong> (starting with 5,000 and doubling N’s value until 160,000 <strong>including</strong>), do the work defined below:</li>

</ul>

<strong>Repeat the following steps 5 times </strong>(i.e. 5 times for <u>each</u> N-value):




<ol>

 <li>Create 4 copies of a list of N random integer values in the range [0, N-1], saving them in the <u>first N cells</u> of each of the four arrays (i.e. repeatedly select/generate a random number and save it under the <strong>same</strong> index <strong>in each</strong> of the four arrays).</li>

</ol>

<u>Note</u>: to obtain random integers, you can define a <em>Random</em> class object and call its<em> nextInt  </em>method. You can also use <em>Math </em>class’s <em>random() </em>method; in this case make sure to multiply the result by N and then cast it to an integer.




<ol>

 <li>Run each of the 4 methods of <em>Sorts </em>class (s<em>electionSort, bubbleSort, mergeSort,</em> and <em>quickSort</em>); make sure to <strong><u>give different arrays</u></strong> as a parameter <strong>for different sorts. </strong>Make arrangements to compute the execution time of each method (as described above). Output <strong>ONE line</strong> containing the value of N, followed by the execution times of all 4 sorts, separated by commas or spaces, in a descriptive sentence. For example, your output line may look like this:</li>

</ol>




<strong>                          N=</strong><em>value</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms= </strong><em>time3</em><strong>,   T_qs= </strong><em>time4 </em>

<em> </em>

where <em>value</em> is the current value of N, and <em>time1</em>, <em>time2</em>, <em>time3</em>, <em>time4</em> are the execution time values for <em>selectionSort</em>, <em>bubbleSort</em>, <em>mergeSort,</em> and<em> quickSort </em>correspondingly.

<strong><u>OUTPUT</u></strong>: the output produced by your <em>SortTimes </em>program should look something like this:




<strong>                  Running Times of four sorting algorithms: </strong>




<strong>N=</strong><em>5000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>5000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em><strong> N=</strong><em>5000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em><strong> N=</strong><em>5000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>5000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong> </strong>

<strong>N=</strong><em>10000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>10000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>10000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>10000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>10000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong> </strong>

<strong>N=</strong><em>20000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>20000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>20000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>20000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>20000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>          </strong>

<strong>N=</strong><em>40000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>40000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>40000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>40000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>40000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>




<strong>N=</strong><em>80000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>80000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em><strong> N=</strong><em>80000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>80000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>80000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>




<strong>N=</strong><em>160000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>160000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>160000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>160000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<strong>N=</strong><em>160000</em><strong>:  T_ss=</strong><em>time1</em><strong>,   T_bs=</strong><em>time2</em><strong>,   T_ms=</strong><em>time3</em><strong>,   T_qs= </strong><em>time4</em>

<em> </em>

<strong>                  End of output </strong>




<u>Note</u>: of course instead of all <em>time1, time2, time3, time4</em> terms you’ll have actual <strong>integer</strong> numbers:




<strong><u>Attention:</u></strong> Your output should be <strong>EASY TO READ</strong>; e.g. print a <u>blank line</u> at the end of each iteration of the N-loop (as shown in the above example).

<strong> </strong>

<strong><u>IMPORTANT!</u>  </strong>

<strong> </strong>

<ol>

 <li><strong>A</strong><strong>NALYZE YOUR OUTPUT T</strong><strong>HOROUGHLY. </strong>Make sure that your output reflects the expected behavior for each algorithm. Remember that selection and bubble sorts are expected to execute in O(N<sup>2</sup>) time while mergesort and quicksort are expected to do the job in O(NlogN) time. You should notice that (i) the bubble sort is noticeably <strong>slower</strong> than the selection sort due to the large number of swaps it has to do at each iteration, and (ii) the mergesort is noticeably <strong>slower </strong>than the quicksort due to the fact that at each step of recursion it uses a temporary array for merging the two sorted halves of the list-segment.</li>

</ol>







<ol start="2">

 <li>Prepare a text file called <strong><em>txt</em> </strong>containing the output produced by <em>SortTimes</em> program. <strong><u>You will need to submit this file together with your program.</u></strong> You can get your output in a file if you run the program on the command line and direct your output to the mentioned file:</li>

</ol>

<em>   javac SortTimes.java    java  SortTimes  &gt; times.txt </em>


