Download Link: https://assignmentchef.com/product/solved-ve280-project-2
<br>
<ol>

 <li><strong><u> Hardworking Guy with a Touching Fish Heart… </u></strong></li>

</ol>

Last year, you took an internship at SilverFOCS Inc., making web games in their game department. Life was busy but quite interesting there.

“Why not try a new company this year?”

Finding an internship was not easy for a full-time internationally-educated student in SJTU. Least working hours should not be too many. The company should not be too far. Anyway, you made it, with an internship in this Junior Involution Information &amp; Technology Inc.

The first day of your work…

The time you arrived at the office, the boss was busy playing with his son, running here and there. Your mentor was shouting at some of your co-workers. He stopped to send you an internal link, “Choose one to work on. I will go back to you later.”, then continued on his intense meeting.

You quickly skimmed through the task lists. Most of them were done, with three uncompleted tasks left.

Write a simulation of an animal world

Work on a project named Simple Twitter

Write a chat bot for internal chat application

The simulation of animal world is for your boss 7-year-old naughty boy. You know, kids are energetic and curious about the world. Outside your office, this happy father and his son were still enjoying themselves in a warm, sunny morning.

You thought that Simple Twitter was something like Twitter, but it turns out not to be. The database of Simple Twitter is based on plain texts. You see a lot of files in a mess in the file tree. The project leader is your tough angry mentor over there. And your co-worker never backup the database. They just lost all their data this morning. “No wonder my mentor was so mad now…”

As for the chat bot…The chat application is based on C++, and it also uses plain texts as its database.

“Hard to make a choice…”

At the same time, your friend was playing happily with the repeater bot in Class of  2019 QQ Chat Group. That inspired you. You got some ideas and then started to work on the chat bot.

<ol start="2">

 <li><strong><u> The Bot </u></strong></li>

</ol>

The main task of the bot is to keep waiting for chat messages, receive one, parse it and return a response or do nothing (Fig. 1).

Figure 1: Flow Chart of the bot

The bot has to attend some chat groups. The bot will only accept message from these groups. These groups are stored in a group list. If a message is not from any of the groups, this message will be ignored. The format of the message is introduced in <u>Section 4.3</u>

Each group has its admins. When in one chat group, only the admins can stop the bot.

Here, to simplify the situation, we assume that once the bot is stopped in one group, the program will  be stopped and exit. Actually, in real world, if the bot has been stopped in one group, we can still interact with it in other groups.

The working directory should be the root directory of the project. The root directory is the directory of Makefile or CMakeLists.txt . Otherwise it may have problems with finding data file.

Each time the bot starts, it will load the course data file

load the group list from the file, then according to the file, load details for each group on the list initialize a random seed,

All of them are specified by program arguments as

<h1>3.    Bot Manual</h1>

<strong> NAME                                                                                                                                                          </strong>

<strong>bot</strong> — a chat bot

<strong> SYNOPSIS FOR A COMMAND                                                                                                                </strong>

#<strong>command</strong> [<u>ke</u>y<u>word</u>]

<h2>              DESCRIPTION</h2>

The bot keeps waiting for a message. When a message arrives, it attempts to parse it and return a response or just do nothing.

If the message can be parsed into a known command, it will execute the command. The commands are as follows:

course:     find all the courses that contain the <u>ke</u>y<u>word </u>instructor:    find all the instructors that contain the <u>ke</u>y<u>word </u>help:    show help message time:    show the time when the message was sent stop:    (For group admins only) stop the bot

All commands start with <sub># </sub>. A message is regarded as a command only if it starts with <sub>#</sub> and can be parsed into one of the known commands above. A command is made up of a prefix (#), a command name (shown below), and keywords (optional). Like

Input:

Output:

Sometimes it will admire the message by adding a prefix to the original message. For the prefix, the bot will flip a coin. If the value of the coin is <strong>1</strong> (or head), it will use <strong>Respect</strong>, otherwise it will use <strong>I really admire</strong>. The probability of the overall admire action is defined by <sub>ADMIRE_ROLL</sub> (unit: %). Sample

Input:

Output:

OR

<strong>Please be aware of the space after the prefix </strong>       Otherwise it will do nothing.

<h1>4.    I/O Standard</h1>

<h2>4.1    Data file for courses/instructor</h2>

A sample course data file is provided with the starter files and it looks like

means that you should use <sub>int</sub> to store the number.

Each line below represents one course in the following format

1 [Course code],[Course name],[Instructor]

<strong><u>Note that a comma</u>,<u> with the s</u>y<u>mbol </u></strong><strong><u><sub>“,” </sub></u>,<u> is the separator. There will be no commas in the name/code/instructor</u>,<u> which also applies to all the other file/input.</u></strong>

<h2>4.2    Group list file and group detail file</h2>

A sample group list file is provided with starter files and it looks like

The first line is the path of the directory that contains all the file with group information.

The path is the relative path from the root directory of your project. The root directory is the directory of all your c++ source files.

Make sure that the bot is started at the root directory of the project. Otherwise it may have problems with finding data file.

The second line is the number  of the groups that the bot has attended <sub>n </sub>.

Assume that . 2147483647 is the maximum value of <sub>int </sub>. This is actually not a limit. It means that you should use <sub>int</sub> to store the number.

Starting from the third line, each line represents a group. The group name is a string. (QQ chooses to use negative numbers to represent the id of its chat group and that is the sample here)

For the sample file, the detail file for group -6 is ${PROJECT_ROOT_DIR}/cases/groups/-6

Group detail files are provided with starter files and they look like

Assume that . 2147483647 is the maximum value of <sub>int </sub>. This is actually not a limit. It means that you should use <sub>int</sub> to store the number.

Starting from the second line, each line stands for one admin.

<h2>4.3    Message input</h2>

All the messages come from the standard input in the format given below

Input samples are provided in the starter file named <sub>query </sub>.

If a message is not from any of the groups in the group list, this message will be ignored, which means that the bot will do nothing.

<strong><u>Note that a comma</u>,<u> with the s</u>y<u>mbol </u></strong><strong><u><sub>“,” </sub></u>,<u> is the separator. There will be no commas in time/</u>g<u>roup/user/content.</u></strong>

<h2>4.4    Commands</h2>

<strong><u>No matter what response it will be</u>,<u> add a new line at the end.</u></strong>

<strong>    course                                                                                                                                                                                                              </strong>

Finds all the courses that contain the keyword. It should be case sensitive.

ERROR: Missing keyword:

Find all the instructors that contain the keyword. It should be case sensitive.

ERROR: Missing keyword:

<h1>5.    Errors and Exceptions</h1>

Errors may happen with the command line arguments. In this case, print the error and exit the program

means that all files will be in the right format and each group on group list will have its configuration file.

<h1>6.    Limitations and Notes</h1>

<ol>

 <li>For your convenience, most of the error/prompt messages are written in <sub>h </sub>. You may not define any global variables yourself.</li>

 <li>Randomness will bring much trouble to grading. So we offer two files <sub>cpp</sub> and <sub>rand.h </sub>. Use int flipCoin() to decide which admire prefix to use</li>

</ol>

RespChoice randomResponse() to decide to repeat or to admire or do nothing

<ol start="3">

 <li>Never trust user input. The message content may come in various ways that you would never dream of. If handled well, life will be easier. We make some choices below.</li>

</ol>

#stop is a command.     #stop and  #stop1 is only a plain message. #stop jiit will be the same result as #stop .

#course ve482 is a command but #courseve482 nor #courseve482 ve482 is just a plain message.

#course or #course  should result in an error.

#course         ve482 will be the same as #course ve482 .   In #instructor Namikaze Minato , the keyword is Namikaze Minato .

<ol start="4">

 <li>In writing your code, you may use the following standard header files: &lt;iostream&gt; , &lt;fstream&gt; ,</li>

</ol>

&lt;sstream&gt; , &lt;iomanip&gt; ,  &lt;string&gt; , &lt;cstdlib&gt; and &lt;cassert&gt; .

<ol start="5">

 <li>Pass large structures by reference rather than value. Where appropriate, pass constant references / pointers-to-constant. Do not pass lots of little arguments when you can pass an appropriate, larger structure instead.</li>

 <li>All required output should be sent to the standard output stream; none to the standard error stream.</li>

 <li>You should strive not to duplicate identical or nearly‐identical code, and instead collect such code into a single function that can be called from various places. Each function should do a single job, though the definition of “job” is obviously open to interpretation. Most students write too few functions that are too large.</li>

</ol>

<h1>7.    Source Code Files and Compiling</h1>

There are three code files located in the <sub>starters.zip</sub> from our resources:

rand.h : The header file which defines the random methods rand.cpp : The cpp file which implements the random methods constants.h : The header file which defines all the constants

You should copy this file into your working directory. <strong>DO NOT modify it!</strong>

You need to write three other source code files. bot.h : contains the declarations for all the functions you write

bot.cpp : contains all the implementations of the functions written in <sub>bot.h </sub>main.cpp : should only contain the main function.

After you have written these files, you can type the following command in the terminal to compile the program:

1 g++ -Wall -o bot bot.cpp rand.cpp main.cpp -std=c++11

This will generate a program called <sub>bot</sub> in your working directory. In order to ensure that the online judge compiles your program successfully, you should name you source code files exactly like how they are specified above.