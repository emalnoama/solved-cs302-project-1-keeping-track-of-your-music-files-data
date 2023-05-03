Download Link: https://assignmentchef.com/product/solved-cs302-project-1-keeping-track-of-your-music-files-data
<br>
<strong>Part 1:</strong>

<ol>

 <li>+2 code well formatted, commented, with reasonable variable names</li>

 <li>+3 Name, Git repo, and how to compile above (1 point each).</li>

 <li>+6 Your writeup about the group dynamics as will be explained on Piazza</li>

</ol>

<strong>Part 2:</strong>

We will assign (# correct test cases) / 100 * 29 points, i.e., scale the remaining 29 points based on the gradeall script

<strong>lib info – A program to help you parse your music library.</strong>

In this assignment, you will be working on a file that contains information about MP3 files. An example is in the file <strong>Music.txt </strong><strong>(</strong><a href="http://www.cs.utk.edu/-plankiplankiclasses/cs302/Labs/Lab1/Music.bct)"><strong>http://www.cs.utk.edu/-plankiplankiclasses/cs302/Labs/Lab1/Music.bct)</strong></a><strong>. </strong>It is in a very specific format. Each line of standard input contains exactly six words that describe a song that is in my MP3 library:

For example, here are the first ten lines of <strong>Music.txt (</strong><a href="http://www.cs.utk.edui-plank/plank/classesics302/Labs/Labl/Music.txt):"><strong>http://www.cs.utk.edui-plank/plank/classesics302/Labs/Labl/Music.txt):</strong></a><strong>Title                Time (m:ss)                                                               </strong><strong>Artist                                     </strong><strong>Album                              </strong><strong>Genre                       </strong><strong>Track </strong>                 i




<strong>                                                                                                                                             </strong><strong>CS302 — Project 1</strong>

<table>

 <tbody>

  <tr>

   <td width="968"><strong>Back_In_Black 4:15 AC DC Back_In_Black Rock 6</strong><strong>Larks’_Tongues_In_Aspic,_Part_III 5:56 King_Crimson Three_of_a_Perfect_Pair Rock 9</strong><strong>Ravel,_Menuet_Antique 5:28 Casadesus,_Robert Ravel,_Complete_Piano_Music,_Disc_2 Classical 8</strong><strong>Pungee 3:02 Meters,_The Look-Ka_Py_Py Rock 3 </strong><strong>Naima 4:24 Coltrane,_John Giant_Steps Jazz 6</strong><strong>Rachmaninoff,_Piano_Concerto_#3_in_Dm,_Opus_30,_2._Intermezzo_-_Adagio 11:43 Berman,_Lazar Rachmaninoff_-_Piano_Concerto_#3 Classical 2 Grieg,_Norwegian_Melodie,_EG_108,_#44,_Sailor’s_Song_-_Hurrah_For_Jonas_Anton_Hjelm 0:32 Steen-Nokleberg,_Einar Grieg_Piano_Music,_Volume_05 Classical 45 Beethoven,_Sonata_#12_in_Ab,_Opus_26,_2._Scherzo._Allegro_molto 2:51 Richter,_Sviatoslav Russian_Piano_School,_V06 Classical 9</strong><strong>Your_Cheatin’_Heart 2:44 Armstrong,_Louis Highlights_From_His_Decca_Years,_Disc_2 Jazz 11</strong><strong>Pieces_Of_Dreams 5:19 Turrentine,_Stanley More_Than_A_Mood Jazz 6</strong></td>

  </tr>

 </tbody>

</table>

And here’s a small file for testing, <strong>Small.txt (http://www.cs.utk.edu/—plank/plank/classes/cs302/Labs/Labl/Small.bct):</strong>

<table>

 <tbody>

  <tr>

   <td width="387"><strong>Countdown 2:25 Coltrane,_John Giant_Steps Jazz 3 Down_In_Brazil 6:07 Walton,_Cedar Naima Jazz 4 Giant_Steps 4:02 Puente,_Tito El_Rey Jazz 5 Giant_Steps 4:46 Coltrane,_John Giant_Steps Jazz 1 Mr._P.C. 7:02 Coltrane,_John Giant_Steps Jazz 7 Naima 4:24 Coltrane,_John Giant_Steps Jazz 6</strong><strong>Naima 5:16 Lyle,_Bobby Night_Breeze Jazz 5 Naima 5:36 Tjader,_Cal A_Fuego_Vivo Jazz 6 Naima 7:49 Walton,_Cedar Naima Jazz 6</strong><strong>Naima 8:38 Walton,_Cedar Eastern_Rebellion Jazz 2 This_Guy’s_In_Love_With_You 8:10 Walton,_Cedar Naima Jazz 2</strong></td>

  </tr>

 </tbody>

</table>

None of the words have spaces — where there should be a space, there is instead an underscore.

Your group’s job is to write the program <strong>lib_info.cpp, </strong>which will be called with a single command line argument: lib_info <em>file</em>

The argument <em>file </em>is a file in the format of <strong>Music.txt. </strong>You do not have to error-check this file; assume that it is in the correct format, and that no combination of artist/album has songs with the same track number.

The first thing your program is going to do is read in all the information and turn all underscores back into spaces.

Next, <strong>lib_info </strong>is going to print out all of MP3 files in the following format: For each artist (sorted lexicographically), the program will print out the artist name, followed by a colon and space, then the number of songs that have that artist’s name, followed by a comma and a space, and then the total time of all songs that have that artist’s name.

After each artist, you will print out each album by that artist, sorted lexicographically (and indented by eight spaces), followed again by the number of songs and total time for that album.

After each album, you will print out the title of each song on that album, sorted by track number. The format of each of these lines will be 16 spaces, the track number, a period, a space, the song’s name, a colon, a space and the song’s time.

Here it is on <strong>Small.txt (http://www.cs.utk.edu/—plank/plank/classesics302/Labs/LabliSmall.bd):</strong>

<strong>7/12/2020                                                                                                                                                                                                                              </strong><strong>CS302 — Project 1</strong>

<strong>UNIX&gt; </strong><strong>lib_info Small.txt</strong>

<strong>Coltrane, John: 4, 18:37</strong>

<strong>Giant Steps: 4, 18:37</strong>

<ol>

 <li><strong> Giant Steps: 4:46</strong></li>

 <li><strong> Countdown: 2:25</strong></li>

 <li><strong>Naima: 4:24</strong></li>

 <li><strong> P.C.: 7:02 </strong><strong>Lyle, Bobby: 1, 5:16</strong></li>

</ol>

<strong>Night Breeze: 1, 5:16</strong>

<ol start="5">

 <li><strong> Naima: 5:16 Puente, Tito: 1, 4:02</strong></li>

</ol>

<strong>El Rey: 1, 4:02</strong>

<ol start="5">

 <li><strong>Giant Steps: 4:02</strong></li>

</ol>

<strong>Tjader, Cal: 1, 5:36</strong>

<strong>A Fuego Vivo: 1, 5:36</strong>

<ol start="6">

 <li><strong>Naima: 5:36 </strong><strong>Walton, Cedar: 4, 30:44</strong></li>

</ol>

<strong>Eastern Rebellion: 1, 8:38</strong>

<ol start="2">

 <li><strong> Naima: 8:38 Naima: 3, 22:06</strong></li>

 <li><strong> This Guy’s In Love With You: 8:10</strong></li>

 <li><strong> Down In Brazil: 6:07</strong></li>

 <li><strong> Naima: 7:49</strong></li>

</ol>

<strong>UNIX&gt;</strong>

<strong>The Grading Script</strong>

To reinforce use of Github in this assignment, two scripts you should use for testing are on the course repository. From the command line in your EECS account, type: <strong>git clone </strong><a href="https://github.com/semrich/ds302_20.git"><strong>https://github.com/semrich/ds302_20.git</strong></a><strong> cs302</strong>

After you clone (make a copy) of this online repository, under <strong>Proj1 </strong>there are two programs that you should use for testing and grading. The first is <strong>gradescript. </strong>Call it with a number between 1 and 100. Each call tests your program on a different input file. Note that although the scripts are in Git, the actual test cases are on the EECS machines so this only will work on those systems. The second script is <strong>gradeall. </strong>This runs all 100 tests at once.

Here’s an example of doing the gradescript. Get into a fresh directory and copy your program to that directory:

<strong>UNIX&gt; is </strong><strong>lib_info </strong><strong>UNIX&gt; gradescript 1</strong>

<strong>Problem 001 is correct.</strong>

<strong>Test: ./lib_info /home/plank/cs302/Labs/Lab1/Gradescript-Examples/001.txt </strong><strong>UNIX&gt;</strong>

This tells you that the test was running <strong>lib_info </strong>on the EECS file <strong>/home/plank/cs302/Labs/Lab1/Gradescript-Examples/001.bct. </strong>Your output was correct. Yay.




<strong>7/12/2020                                                                                                                                                                                                                             </strong><strong>CS302 — Project </strong><strong>1</strong>

<strong>The gradescript tests correctness by running the program from last fall, and comparing your output with what has been historically used for assessment in this course. The </strong><strong>comparison is </strong><em>exact, </em><strong>so your output must be identical to the benchmark, character for character. Let’s see what happens when it’s not.</strong>

<strong>Suppose your lib_info prints an extra space after the album name. Then, when you run the gradescript, it will flag an error:</strong>

<strong>UNIX&gt; </strong><strong>gradescript 1 </strong><strong>Problem 001 is incorrect.</strong>

<strong>Your standard output does not match the correct one.</strong>

<strong>TEST:</strong>

<strong>./lib_info /home/plank/cs302/Labs/Lab1/Gradescript-Examples/001.txt </strong><strong>FILES:</strong>

<strong>Your standard output is in tmp-001-test-stdout.txt.</strong><strong>Your standard error is in tmp-001-test-stderr.txt.</strong>

<strong>The correct standard output is in tmp-001-correct-stdout.txt.</strong><strong>The correct standard error is in tmp-001-correct-stderr.txt.</strong>

<strong>Look at correct files and your files, perhaps run ‘diff -y’ on them, and figure out your mistake. Please remember to delete this files when you are finished.</strong>

<strong>UNIX&gt;</strong>

<strong>Usually, when this happens, the first thing to do is take a look at the input file, and your output compared to the benchmark output:</strong>

<strong>UNIX&gt; </strong><strong>cat /home/plank/cs302/Labs/Lab1/Gradescript-Examples/001.txt</strong>

<strong>Pusherman 5:06 Mayfield,_Curtis Superfly Rock 2</strong>

<strong>UNIX&gt; </strong><strong>./lib_info /home/plank/cs302/Labs/Lab1/Gradescript-Examples/001.txtMayfield, Curtis: 1, 5:06</strong>

<strong>Superfly: 1, 5:06</strong>

<ol start="2">

 <li><strong> Pusherman: 5:06</strong></li>

</ol>

<strong>UNIX&gt; </strong><strong>/home/plank/cs302/Labs/Lab1/lib_info /home/plank/cs302/Labs/Lab1/Gradescript-Examples/001.txt</strong>

<strong>Mayfield, Curtis: 1, 5:06 </strong><strong>Superfly: 1, 5:06</strong>

<ol start="2">

 <li><strong> Pusherman: 5:06</strong></li>

</ol>

<strong>UNIX&gt;</strong>

<strong>The file is simple enough, and both outputs look identical. Dang. The next thing to do is to look at the files that gradescript creates when there is an error. There are four such files</strong>

<strong>— tmp-001-correct-stdout.bct and tmp-001-correct-stderr.bct are standard output and standard error of the correct program, and tmp-001-test-stdout.txt and tmp-001-test­stderr.txt are standard output and standard error of the erroneous program. First, list them:</strong>




<strong>7/12/2020                                                                                                                                                     </strong><strong>CS302 — Project 1</strong>

<strong>UNIX&gt; </strong><strong>is -1</strong>

total 72

<ul>

 <li>rwxr-xr-x 1 plank loci 58689 2011-08-14 14:46 lib_info</li>

 <li>rw-r–r– 1 plank loci 0 2011-08-14 14:52 tmp-001-correct-stderr.txt</li>

 <li>rw-r–r– 1 plank loci 87 2011-08-14 14:52 tmp-001-correct-stdout.txt</li>

 <li>rw-r–r– 1 plank loci 0 2011-08-14 14:52 tmp-001-test-stderr.txt</li>

 <li>rw-r–r– 1 plank loci 88 2011-08-14 14:52 tmp-001-test-stdout.txtUNIX&gt;</li>

</ul>

Neither program produces output on standard error. The sizes on the two <strong>stdout </strong>files differ by one. That should give you a clue. Now, run <strong>diff -y </strong>on them:

UNIX&gt; <strong>diff -y tmp-001-correct-stdout.txt tmp-001-test-stdout.txt</strong>

Mayfield, Curtis: 1, 5:06                                          Mayfield, Curtis: 1, 5:06

Superfly: 1, 5:06                                        1          Superfly: 1, 5:06

<ol start="2">

 <li>Pusherman: 5:06 2. Pusherman: 5:06</li>

</ol>

<strong>UNIX&gt;</strong>

<strong>diff -y </strong>prints both files and flags where they differ. Here, it’s line two, which is denoted by a vertical bar. They still look the same to me. At this point, <strong>I </strong>sometimes print just the offending line to see if I see a difference:

UNIX&gt; <strong>sed -n 2p tmp-001-test-stdout.txt</strong>

Superfly: 1, 5:06

UNIX&gt; <strong>sed </strong><strong>–</strong><strong>n 2p tmp</strong><strong>–</strong><strong>001</strong><strong>–</strong><strong>correct</strong><strong>–</strong><strong>stdout.txt</strong>

Superfly: 1, 5:06

<strong>UNIX&gt;</strong>

Dang. Still no difference. Now try piping the output to <strong>cat </strong><strong>–</strong><strong>eT, </strong>which identifies tabs and the end of each line:

UNIX&gt; <strong>sed -n 2p tmp-001-test-stdout.txt 1 cat -et </strong>Superfly: <strong>1, </strong>5:06 $

UNIX&gt; <strong>sed </strong><strong>–</strong><strong>n 2p tmp</strong><strong>–</strong><strong>001</strong><strong>–</strong><strong>correct</strong><strong>–</strong><strong>stdout.txt 1 cat </strong><strong>–</strong><strong>et </strong>Superfly: <strong>1, </strong>5:06$

<strong>UNIX&gt;</strong>

There it is! There’s an extra space at the end of the line. Now, I know from experience that y’all find the process of matching exaxt output formatting tedious. We agree — however, meeting specifications is a large part of programming correctly, in teams, competitive programming (e.g., HackerRank) and some code test platforms used in the hiring process. We won’t always make you match output exactly, but you will have to here.

<strong>Help and steps</strong>

You don’t need to read this part if you want to try to do the lab without help or guidance. However, if you want some help, the prior document from Dr. Plank has the following structs for songs, albums and artists (he defined them as classes, but it violates convention in the more OOP-oriented C++ that we will use this term). For this assignment you can use structs, i.e., making a custom C++ class is optional. Using STL maps (see below) makes this assignment much more simple since you can hash on strings on multiple levels. I’ve kept this mostly as from last Fall but noted differences in my solution as comments in the code below.<strong>                                                                                                                                         </strong>

<table>

 <tbody>

  <tr>

   <td width="376"><strong>struct Song {</strong><strong>string title;</strong><strong>int time; // could also be a string </strong><strong>int track;</strong>};<strong>struct Album {</strong><strong>map &lt;int, Song &gt; songs;</strong><strong>string name;</strong><strong>int time;</strong><strong>int nsongs; // optional variable but makes it easier</strong>} ;<strong>struct Artist {</strong><strong>map &lt;string, Album &gt; albums; </strong><strong>string name;</strong><strong>int time;</strong><strong>int nsongs;</strong>} ;</td>

  </tr>

 </tbody>

</table>

I like this assignment, esp. as a collaborative one, since 50% of it is relatively easy to run off and do (proven on 1/9 before picking up my son) but to fully meet the spec you need to ** think ** before you code. My final reference code is about 120 lines with file I/O and comments, including about 10 lines citing StackOverflow that I referred to to remind myself how to use sscanf and iteratate through a container (but you can use whatever method and/or refresher material from CS140).

<strong>Although my code/process was different than Plank’s, I followed largely the same steps using the Small file listed above. </strong>So <strong>I </strong>have included them for your reference.

Step 1

Write the main code that reads the lines of text. Convert each time to an integer and test. I have some other test files to help:

<ul>

 <li><strong>txt (http://www.cs.utk.edu/—plank/plank/classes/cs302/Labs/Labl/Lark.bct) — </strong>all lines with the word “Lark”.</li>

 <li><strong>txt (http://www.cs.utk.edu/—plank/plank/classes/cs302/Labs/Labl/Rhapsody.bct) — </strong>four renditions of “Rhapsody in Blue.”</li>

 <li><strong>txt (http://www.cs.utk.edu/—plank/plank/classes/cs302/Labs/Labl/Dreaming.bct) — </strong>a Dave Matthews album — good for testing since it has a track #34.</li>

</ul>

Let’s test step 1:




<strong>7/12/2020                                                                                                                                                    </strong><strong>CS302 — Project 1</strong>

<strong>UNIX&gt; </strong><strong>cat Rhapsody.txt</strong>

<strong>Gershwin,_Rhapsody_In_Blue 13:22 Gershwin,_George Masters_of_the_Roll,_Volume_05 Classical 1</strong>

<strong>Gershwin,_Rhapsody_In_Blue_(Piano_Solo) 13:45 Gershwin,_George George_Gerswin_plays_Rhapsody_In_Blue_and_his_Other_Favorite_Pieces Classical 1 </strong><strong>Gershwin,_Rhapsody_in_Blue 14:48 Finkel,_Elliot Rhapsody Classical 9</strong>

<strong>Gershwin,_Rhapsody_in_Blue 12:56 Gershwin,_George Legendary_Piano_Immortals,_Record_4 Classical 1</strong>

<strong>UNIX&gt; </strong><strong>step_l Rhapsody.txt</strong>

<table>

 <tbody>

  <tr>

   <td width="59"><strong>13:22</strong></td>

   <td width="12"><strong>=</strong></td>

   <td width="25"><strong>802</strong></td>

   <td width="12"><strong>=</strong></td>

   <td width="792"><strong>13:22</strong></td>

  </tr>

  <tr>

   <td width="59"><strong>13:45</strong></td>

   <td width="12"><strong>=</strong></td>

   <td width="25"><strong>825</strong></td>

   <td width="12"><strong>=</strong></td>

   <td width="792"><strong>13:45</strong></td>

  </tr>

  <tr>

   <td width="59"><strong>14:48</strong></td>

   <td width="12"><strong>=</strong></td>

   <td width="25"><strong>888</strong></td>

   <td width="12"><strong>=</strong></td>

   <td width="792"><strong>14:48</strong></td>

  </tr>

  <tr>

   <td width="59"><strong>12:56</strong></td>

   <td width="12"><strong>=</strong></td>

   <td width="25"><strong>776</strong></td>

   <td width="12"><strong>=</strong></td>

   <td width="792"><strong>12:56</strong></td>

  </tr>

 </tbody>

</table>




<strong>UNIX&gt;</strong>

<strong>Step 2</strong>

<strong>Convert all the underscores to spaces when you read words in. Then, create the song struct instance when you read a song, and print it:</strong>




7/12/2020                                                                                                                                                    CS302 — Project 1

UNIX&gt; <strong>step_2 Rhapsody.txt</strong>

Gershwin, Rhapsody In Blue 1 13:22

Gershwin, Rhapsody In Blue (Piano Solo) 1 13:45

Gershwin, Rhapsody in Blue 9 14:48 Gershwin, Rhapsody in Blue 1 12:56 UNIX&gt; <strong>cat Dreaming.txt</strong>

Satellite 4:51 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 3

Jimi_Thing 5:57 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 9

Typical_Situation 5:59 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 5

Ants_Marching 4:31 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 7

Pay_for_What_You_Get 4:32 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 11

The_Best_of_What’s_Around 4:17 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 1

Dancing_Nancies 6:05 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 6

Rhyme_&amp;_Reason 5:15 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 4

Lover_Lay_Down 5:37 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 8

What_Would_You_Say 3:42 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 2

#34 4:58 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 34

Warehouse 7:06 Matthews,_Dave,_Band Under_the_Table_and_Dreaming Rock 10

UNIX&gt; <strong>step_2 Dreaming.txt</strong>

Satellite 3 4:51

Jimi Thing 9 5:57

Typical Situation 5 5:59

Ants Marching 7 4:31

Pay for What You Get 11 4:32

The Best of What’s Around 1 4:17 Dancing Nancies 6 6:05

Rhyme &amp; Reason 4 5:15

Lover Lay Down 8 5:37

What Would You Say 2 3:42

#34 34 4:58

Warehouse 10 7:06

UNIX&gt;

<strong>Step 3</strong>

<strong>This is a sanity check depending on what C++ compiler you are using. Having tested on the lab machines, the default constructor(s) work as intended and you can use the </strong><strong>overloaded subscript operator (0) based on the key (string) without worrying about if the artist has been seen. This is here to help think more simply about the maps that underlie this assignment.</strong>

<strong>Dr. Plank recommends at this stage you should have an artist map with all of the artist data. For this check, when you read in a song, you should check for the artist in the map. If it is there, print “Old Artist” and the name. If it is not, create the artist, set its name, put it into the map and print “New Artist” and the name. Test:</strong>




UNIX&gt; <strong>step_3 Dreaming.txt</strong>

New Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band Old Artist: Matthews, Dave, Band UNIX&gt; <strong>step_3 Rhapsody.txt</strong>

New Artist: Gershwin, George Old Artist: Gershwin, George New Artist: Finkel, Elliot

Old Artist: Gershwin, George UNIX&gt; <strong>cat Lark.txt</strong>

Larks’_Tongues_In_Aspic,_Part_III 5:56 King_Crimson Three_of_a_Perfect_Pair Rock 9

Between_the_Devil_and_the_Deep_Blue_Sea 2:44 Larkins,_Ellis Jazz_Piano_III_(A_Smithsonian_Collection) Jazz 2

Exiles 5:47 King_Crimson Larks’_Tongues_In_Aspic Rock 3

Larks’_Thrak 2:37 League_of_Crafty_Guitarists Intergalactic_Boogie_Express Rock 3

Schubert-Liszt,_Hark,_Hark,_The_Lark 3:03 Paderewski,_Ignace Josef_Hofmann_&amp;_Ignace_Jan_Paderewski_Play_Liszt Classical 5 Larks’_Tongues_In_Aspic,_Part_2 6:57 King_Crimson Larks’_Tongues_In_Aspic Rock 6

Book_of_Saturday 2:49 King_Crimson Larks’_Tongues_In_Aspic Rock 2

Schubert-Liszt,_Hark,_Hark_the_Lark 2:57 Paderewski,_Ignace Paderewski_Plays_Concert_No.1 Classical 7

Balakirev,_The_Lark 5:25 Lewin,_Michael A_Russian_Piano_Recital Classical 2

UNIX&gt; <strong>step_3 Lark.txt</strong>

New Artist: King Crimson

New Artist: Larkins, Ellis

Old Artist: King Crimson

New Artist: League of Crafty Guitarists New Artist: Paderewski, Ignace

Old Artist: King Crimson

Old Artist: King Crimson

Old Artist: Paderewski, Ignace New Artist: Lewin, Michael

UNIX&gt;

<strong>Step 4</strong>

<strong>Do the same with the album in the artist’s struct. Check to see if the album is there. If so, print out its name. If not, create it and print out its name. Test:</strong>




UNIX&gt; <strong>step_4 Dreaming.txt</strong>

New Artist: Matthews, Dave, Band

New Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming Old Artist: Matthews, Dave, Band

Old Album: Under the Table and Dreaming UNIX&gt; <strong>step_4 Lark.txt</strong>

New Artist: King Crimson

New Album: Three of a Perfect Pair New Artist: Larkins, Ellis

New Album: Jazz Piano III (A Smithsonian Collection)

Old Artist: King Crimson

New Album: Larks’ Tongues In Aspic

New Artist: League of Crafty Guitarists New Album: Intergalactic Boogie Express New Artist: Paderewski, Ignace

New Album: Josef Hofmann &amp; Ignace Jan Paderewski Play Liszt Old Artist: King Crimson

Old Album: Larks’ Tongues In Aspic Old Artist: King Crimson

Old Album: Larks’ Tongues In Aspic Old Artist: Paderewski, Ignace

New Album: Paderewski Plays Concert No. 1 New Artist: Lewin, Michael

New Album: A Russian Piano Recital UNIX&gt;




<strong>7/12/2020                                                                                                                                                    </strong><strong>CS302 — Project 1</strong>

<strong>Step 5</strong>

<strong>Insert the songs into the albums’ song lists. Write code to traverse the artists/albums after you’re finished reading the information from the file. Just print out names — don’t worry about songs or times yet. Test:</strong>

UNIX&gt; <strong>step_5 Dreaming.txt</strong>

Matthews, Dave, Band

Under the Table and Dreaming

UNIX&gt; <strong>step_5 Rhapsody.txt</strong>

Finkel, Elliot

Rhapsody

Gershwin, George

George Gerswin plays Rhapsody In Blue and his Other Favorite Pieces

Legendary Piano Immortals, Record 4

Masters of the Roll, Volume 05

UNIX&gt; <strong>step_5 Lark.txt</strong>

King Crimson

Larks’ Tongues In Aspic

Three of a Perfect Pair

Larkins, Ellis

Jazz Piano III (A Smithsonian Collection)

League of Crafty Guitarists

Intergalactic Boogie Express

Lewin, Michael

A Russian Piano Recital

Paderewski, Ignace

Josef Hofmann &amp; Ignace Jan Paderewski Play Liszt

Paderewski Plays Concert No. 1

UNIX&gt; <strong>step_5 Small.txt</strong>

Coltrane, John

Giant Steps

Lyle, Bobby

Night Breeze

Puente, Tito

El Rey Tjader, Cal

A Fuego Vivo

Walton, Cedar

Eastern Rebellion

Naima

<strong>UNIX&gt;</strong>

<strong>Step 6</strong>

<strong>Print out the songs too, and print them out in the correct format, with track number and time:</strong>

<strong>7/12/2020                                                                                                                                                     </strong><strong>CS302 — Project 1</strong>

UNIX&gt; <strong>step_6 Rhapsody.txt</strong>

Finkel, Elliot

Rhapsody

<ol start="9">

 <li>Gershwin, Rhapsody in Blue: 14:48</li>

</ol>

Gershwin, George

George Gerswin plays Rhapsody In Blue and his Other Favorite Pieces

<ol>

 <li>Gershwin, Rhapsody In Blue (Piano Solo): 13:45</li>

</ol>

Legendary Piano Immortals, Record 4

<ol>

 <li>Gershwin, Rhapsody in Blue: 12:56</li>

</ol>

Masters of the Roll, Volume 05

<ol>

 <li>Gershwin, Rhapsody In Blue: 13:22</li>

</ol>

UNIX&gt; <strong>step_6 Lark.txt</strong>

King Crimson

Larks’ Tongues In Aspic

<ol start="2">

 <li>Book of Saturday: 2:49</li>

 <li>Exiles: 5:47</li>

 <li>Larks’ Tongues In Aspic, Part 2: 6:57</li>

</ol>

Three of a Perfect Pair

<ol start="9">

 <li>Larks’ Tongues In Aspic, Part III: 5:56</li>

</ol>

Larkins, Ellis

Jazz Piano III (A Smithsonian Collection)

<ol start="2">

 <li>Between the Devil and the Deep Blue Sea: 2:44</li>

</ol>

League of Crafty Guitarists Intergalactic Boogie Express

<ol start="3">

 <li>Larks’ Thrak: 2:37</li>

</ol>

Lewin, Michael

A Russian Piano Recital

<ol start="2">

 <li>Balakirev, The Lark: 5:25</li>

</ol>

Paderewski, Ignace

Josef Hofmann &amp; Ignace Jan Paderewski Play Liszt

<ol start="5">

 <li>Schubert-Liszt, Hark, Hark, The Lark: 3:03</li>

</ol>

Paderewski Plays Concert No. 1

<ol start="7">

 <li>Schubert-Liszt, Hark, Hark the Lark: 2:57</li>

</ol>

UNIX&gt;

<strong>Step 7</strong>

<strong>Let’s worry about the album total time. When you’re reading in a song, update the album’s time. Make sure you set the album’s time to zero when you creat the album. Test it by </strong><strong>printing out the correct line for each album. Note, you don’t need to keep track of the number of songs, because you have that information already in the </strong><strong>songs </strong><strong>map. Test:</strong>




<strong>7/12/2020                                                                                                                                                    </strong><strong>CS302 — Project 1</strong>

UNIX&gt; <strong>step_7 Rhapsody.txt</strong>

Finkel, Elliot

Rhapsody: 1, 14:48

<ol start="9">

 <li>Gershwin, Rhapsody in Blue: 14:48</li>

</ol>

Gershwin, George

George Gerswin plays Rhapsody In Blue and his Other Favorite Pieces: 1, 13:45

<ol>

 <li>Gershwin, Rhapsody In Blue (Piano Solo): 13:45</li>

</ol>

Legendary Piano Immortals, Record 4: 1, 12:56 1. Gershwin, Rhapsody in Blue: 12:56

Masters of the Roll, Volume 05: 1, 13:22

<ol>

 <li>Gershwin, Rhapsody In Blue: 13:22</li>

</ol>

UNIX&gt; <strong>step_7 Dreaming.txt</strong>

Matthews, Dave, Band

Under the Table and Dreaming: 12, 62:50

<ol>

 <li>The Best of What’s Around: 4:17</li>

 <li>What Would You Say: 3:42</li>

 <li>Satellite: 4:51</li>

 <li>Rhyme &amp; Reason: 5:15</li>

 <li>Typical Situation: 5:59</li>

 <li>Dancing Nancies: 6:05</li>

 <li>Ants Marching: 4:31</li>

 <li>Lover Lay Down: 5:37</li>

 <li>Jimi Thing: 5:57</li>

 <li>Warehouse: 7:06</li>

 <li>Pay for What You Get: 4:32</li>

 <li>#34: 4:58</li>

</ol>

<strong>UNIX&gt;</strong>

<strong>The final step:</strong>

<strong>Write the code to update the artist’s song count and total time when you read in a song. Then print out the correct line for each artist. Test, comment, and you’re done.</strong>