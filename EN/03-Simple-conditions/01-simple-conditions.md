[slide]
# Chapter 3.1. Simple Conditions

In this chapter, we will discuss the **conditional constructions in the C # language**, through which our program may have different effects, depending on a condition. We'll explain the syntax of conditional operators for checks (**`if`** and **`if-else`**) with appropriate examples and we will see in what range one variable (its **scope**) lives. Finally, we will go through **debugging** techniques to track the path that runs through our program during implementation.

## Video

[youtube-video videoId=uwW_ueaOt7M /]

[/slide]

[slide]
## Comparing numbers

In programming, we can compare values using the following **operators**:

* Operator **`<`** (less than)
* Operator **`>`** (greater than)
* Operator **`<=`** (less than or equals)
* Operator **`>=`** (greater than or equals)
* Operator **`==`** (equals)
* Operator **`!=`** (inequals)

When compared the result is boolean value **true** or **false**, depending on whether the result of the comparison is true or false.

### Examples of comparing numbers

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Comparing-numbers-01.png alt="Code" /]

Note that when printing the **true** and **false** values in C # language, they are printed with a capital letter, respectively **True** and **False**.
[/slide]

[slide]
### Comparison operators

In C #, we can use the following comparison operators:

<table>
<tr>
<th>Operator</th> <th>Notation</th> <th>Applicable for</th>
</tr>
<tr>
<td>Equals</td><td align="center"> == </td><td rowspan="2"> numbers, strings, dates</td>
</tr>
<tr>
<td>Not equals</td><td align="center"> != </td>
</tr>
<tr>
<td>Greater than</td><td align="center"> > </td><td rowspan="4">numbers, dates, other comparable objects</td>
</tr>
<tr>
<td>Greater than or equals</td><td align="center"> >= </td>
</tr>
<tr>
<td>Less than</td><td align="center"> &lt; </td>
</tr>
<tr>
<td>Less than or equals</td><td align="center"> &lt;= </td>
</tr>
</table>

Example:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Comparing-numbers-02.png alt="Code" /]
[/slide]

[slide]
## Simple conditions

In programming we often **check the conditions** and perform different actions, depending on the result of the check. This is done by **if** verification, which has the following construction:

```csharp
if (condition)
{
    // condition body;  
}
```

### Example: excellent grade

We read the grade from the console and check if it's excellent (**`≥ 5.50`**).

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/01.Еxcellent-result-01.png alt="Code" /]

Test the code from the example locally. Try entering different grades, for example **4.75**, **5.49**, **5.50** and **6.00**. For grades **less than 5.50**, the program will not give any output, however if the grade is **5.50 or greater**, the output would be "**Excellent!**".

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]		

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#0]           
                            https://judge.softuni.bg/Contests/Practice/Index/506#0
                         [/anchor].
[/slide]

[slide]
## The if-else statement

The **`if`** construction may also contain an **`else`** clause to give a specific action in case the boolean expression (which is set at the beginning **`if (boolean expression)`** ) returns a negative result (**`false`**). Built this way, **the conditional construction** is called **`if-else`** and its behavior is as follows: if the result of the condition is **positive** (**`true`**) - we perform some actions, a when it is **negative** (**`false`**) - others. The format of the construction is:

```csharp
if (condition)
{
    // condition body;
}
else
{
    // еlse construction body;
}

```
[/slide]

[slide]
### Example: excellent grade or not

Like the example above, we read the grade from the console and check if it's excellent, but this time we should **output the result in both cases**.

[task]  
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
        var grade = double.Parse(Console.ReadLine());
        // TODO
    [/task-description]
[/task]			

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/02.Excellent-or-not-01.png alt="Code" /]

#### Testing in judge system

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#1]           
                            https://judge.softuni.bg/Contests/Practice/Index/506#1
                         [/anchor].
[/slide]

[slide]
### For curly braces {} after if / other

When we have **only one command** in the body of the ** if construction**, we can **skip the curly brackets**, indicating the conditional operator body. When we want to execute **block of code** (group of commands), curly brackets are **required**. In case we drop them, **only the first line**  after **if clause** will be executed.

<table><tr><td><img src="https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/alert-icon.png" style="max-width:50px" /></td>
<td>It's a good practice to <strong>always put curly braces,</strong> because it makes our code more readable and clean.</td>
</tr></table>

Here is an example where dropping curly braces leads to confusion:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Brackets-tip-01.png alt="Code" /]

Execute the above code will output the following console result:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Brackets-tip-03.png alt="Console" /]

With curly braces:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Brackets-tip-02.png alt="Code" /]

The following output will be printed on the console:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Brackets-tip-04.png alt="Console" /]
[/slide]

[slide]
### Example: even or odd

Write a program that checks whether an integer is **even** or **odd**.

[task]  
    [code-editor language=csharp]
        var num = int.Parse(Console.ReadLine());
        if (num % 2 == 0)
        // TODO
    [/code-editor]

    [task-description]
    We can solve the problem with one **`if-else`** construction and the operator **`%`**, which returns a **remainder by dividing** from two numbers.
    [/task-description]
[/task]			

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#2]           
                            https://judge.softuni.bg/Contests/Practice/Index/506#2
                         [/anchor].
[/slide]

[slide]
### Example: the larger number

Write a program that reads from the console two integers and takes the larger of them.

[task]  
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
    Our first task is to **read** the two numbers from the console. Then, with a simple **`if-else`** construction, combined with the **operator for greater than** (**`>`**), we do check. Part of the code is deliberately blurred to test what we have learned so far.
    [/task-description]
[/task]		

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/04.Greater-number-02.png alt="Code" /]

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#3]           
							https://judge.softuni.bg/Contests/Practice/Index/506#3
						 [/anchor].
[/slide]

[slide]
## Life of a variable

Each variable has a range in which it exists, called **variable scope**. This range specifies where a variable can be used. In the C # language, the area in which a variable exists, starts from the order in which we **defined it** and ends with the first closing curly bracket **}** (of the method, the **if construction** and etc.). For this, it is important to know that **any variable defined inside the body of `if` will not be available outside** of it unless we have defined it higher in the code.

In the example below, on the last line we are trying to print the variable **salary** that is defined in the **if construction**, we will get an **error** because we don't have access to her.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Variable-scope-01.png alt="Code" /]
[/slide]

[slide]
## Sequence of conditions

Sometimes we need to do a sequnce of conditions before we decide what actions our program will execute. In such cases, we can apply the construct **`if-else if ... -else`** **in serie**. For this purpose we use the following format:

```csharp
if (condition)
{
    // condition body;
}
else if (second condition)
{
    // condition body;
}
else if (third condition)
{
    // condition body;
}
…
else
{
    // else construction body;
}
```
[/slide]

[slide]
### Example: digit in english

Print the digits in the range of 1 to 9 (the digit is read from the console). We can read the digit and then, through a **sequence of conditions** we print the relevant english word:

[task]  
    [code-editor language=csharp]
        int num = int.Parse(Console.ReadLine());

        if (num == 1)
        {
            Console.WriteLine("one");
        }
        else if (num == 2)
        {
            Console.WriteLine("two");
        }
        else if (…) 
        {
            …
        } 
        else if (num == 9)
        {
            Console.WriteLine("nine");
        } 
        else 
        {
            Console.WriteLine("number too big");
        }
    [/code-editor]
[/task]

The program logic from the above example **sequentially compares** the input number from the console with the digits from 1 to 9, when **each sequent comparison is being performed only in case the previous comparison is not true**. Ultimately, if none of the **`if`** conditions are not executed, the last **`else`** **clause`** is.

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#4]           
							https://judge.softuni.bg/Contests/Practice/Index/506#4
						 [/anchor].
[/slide]

[slide]
## Exercises: Simple Conditions

To verified our knowledge of conditional constructions **`if`** and **`if-else`**, we will solve a few practical exercises.

### Problem: bonus score

You have an **integer** - the number of points. **Bonus scores** are charged on it, according to the rules described below. Write a program that calculates **bonus scores** for this figure and **total points** with bonuses.- Ако числото е **до 100** включително, бонус точките са 5.

- If the number is **up to 100** including, bonus points are 5.
- If the number is **larger than 100**, bonus points are **20%** from the number.
- If the number is **larger than 1000**, bonus points are **10%** from the number.
- Additional bonus points (accrues separately from the previous ones):
- for **even** number -> + 1 p.
- for number, that **ends with 5** -> + 2 p.

[task]  
    [code-editor language=csharp]
        var num = int.Parse(Console.ReadLine());
        var bonusScore = 0.0;
        // TODO
    [/code-editor]

    [task-description]
        We can calculate the basic and additional bonus points with a series of **`if-else-if-else`** conditions. For **the main bonus points we have 3 cases** (when the entered number is up to 100, between 100 and 1000 and larger than 1000), and for **extra bonus points - 2 more cases** (when the number is even and odd).
    [/task-description]
[/task]
 
#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 20 | 6<br>26 |
| 175 | 37<br>212 |
| 2703 | 270.3<br>2973.3 |
| 15875 | 1589.5<br>17464.5 |
[/slide]

[slide]
#### Hints and Guidelines

We can calculate the basic and additional bonus points with a series of **`if-else-if-else`** conditions. For **the main bonus points we have 3 cases** (when the entered number is up to 100, between 100 and 1000 and larger than 1000), and for **extra bonus points - 2 more cases** (when the number is even and odd).

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/06.Bonus-score-01.png alt="Code" /]

Here's an example solution::

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/06.Bonus-score-02.png alt="Console" /]

Note that for this exercise, the Judge is set to ignore anything that is not a number, so we can print not only the numbers, but also the specifying text.

#### Testing in the Judge System

Test your solution  here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#3]           
							 https://judge.softuni.bg/Contests/Practice/Index/506#3
						  [/anchor].
[/slide]

[slide]
### Problem: sum seconds

Three athletes finish for a few **seconds** (between **1** and **50**). Write a program that introduces the times of the contestants and calculates their **total time** in "minutes:seconds". Seconds need to be **zeroed at the front** (2 -> "02", 7 -> "07", 35 -> "35").

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 35<br>45<br>44 | 2:04 |
| 22<br>7<br>34 | 1:03 |
| 50<br>50<br>49 | 2:29 |
| 14<br>12<br>10 | 0:36 |

#### Hints and Guidelines

First we sum the three numbers to get the total result in seconds. Since **1 minute = 60** seconds, we will have to calculate the number of minutes and seconds in the range 0 to 59:- Ако резултатът е между 0 и 59, отпечатваме 0 минути + изчислените секунди.
- If the result is between 0 and 59, we print 0 minutes + calculated seconds.
- If the result is between 60 and 119, we print 1 minute + calculated seconds minus 60.
- If the result is between 120 and 179, we print 2 minutes + calculated seconds minus 120.
- If the seconds are less than 10, we print the number with zero in front.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/07.Sum-seconds-01.png alt="Code" /]

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#6]           
							https://judge.softuni.bg/Contests/Practice/Index/506#6
						 [/anchor].
[/slide]

[slide]
### Problem: metric converter

Write a program that **convert a distance** between the following **8 units of measure**: **`m`, `mm`,` cm`, `mi`, `in`, `km`,` ft `,` yd`**. Use the below table:

| Input measure | Output measure |
| :-------------: | :--------------: |
| 1 meter (m) | 1000 millimeters (mm) |
| 1 meter (m) | 100 centimeters (cm) |
| 1 meter (m) | 0.000621371192 miles (mi) |
| 1 meter (m) | 39.3700787 inches (in) |
| 1 meter (m) | 0.001 kilometers (km) |
| 1 meter (m) | 3.2808399 feet (ft)  |
| 1 meter (m) | 1.0936133 yards (yd) |

You have three input lines:

- First line: number for converting.
- Second line: input unit.
- Third line: output unit (the result).

[task]  
    [code-editor language=csharp]
        var size = double.Parse(Console.ReadLine());
        var sourceMetric = Console.ReadLine().ToLower();
        var destMetric = Console.ReadLine().ToLower();

        if (sourceMetric == "km")
        {
            size = size / 0.001;
        }

        // TODO: Check the other metrics
    [/code-editor]

    [task-description]
        We read the input data, and we can add **`.ToLower()`** method when we read the measure units, which will make all letters small.
    [/task-description]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 12 <br>km <br>ft | 39370.0788 |
| 150 <br>mi <br>in | 9503999.99393599 |
| 450 <br>yd <br>km | 0.41147999937455 |

#### Hints and Guidelines

We read the input data, and we can add **`.ToLower()`** method when we read the measure units, which will make all letters small. As we can see from the table in the condition, we can only do converting **between meters and some other measure unit**. Then, first we have to calculate the number for converting in meters. That's why, we need to make a set of checks to define the input unit and then the output unit.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/08.Metric-converter-01.png alt="Code" /]

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#7]           
							https://judge.softuni.bg/Contests/Practice/Index/506#7
						 [/anchor].
[/slide]

[slide]
## Debugging

So far we wrote a lot of code, and there were some mistakes in it, right? Now we will show a tool that can help us to find mistakes easier.

### What is "debugging"?

**Debugging** is the „**attach**“ process to the running program, which allows us to track step by step the process. We can track **line by row** what happens to our program, what path it follows, what are the values of defined variables at each step of debugging, and many other things that allow us to detect errors (**bugs**).

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Debugging-01.png alt="Debugger" /]
[/slide]

[slide]
### Debbuging in Visual Studio

By pressing the [**F10**] button, we run the program in **debug mode**. We move to **the next line** again with [**F10**].

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Debugging-02.png alt="Debugger" /]

With [**F9**] we create stoppers - the so-called **breakpoints**, that we can get directly using [**F5**] when we start the program.
[/slide]

[slide]
## Exercises: simple conditions

Now let's practise the lessons learned in this chapter with a few exercises.

### Empty Visual Studio solution (Blank Solution)

We create a blank solution (**Blank Solution**) in Visual Studio to organize better the task solutions from the exercise  - each task will be in a separate project and all projects will be in common solution.

We run Visual Studio and create new **Blank Solution:** [**File**] -> [**New**] -> [**Project**].

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Visual-studio-01.png alt="Empty VS Solution" /]

Choose from the dialog box [**Templates**] -> [**Other Project Types**] -> [**Visual Studio Solutions**] -> [**Blank Solution**] and give a appropriate project name, for example: “Simple-Conditions”:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Visual-studio-02.png alt="Empty VS Solution" /]

Now we have empty Visual Studio Solution (no projects in it):

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/00.Visual-studio-03.png alt="Empty VS Solution" /]
[/slide]

[slide]
### Problem: excellent grade

The first exercise for this topic is to write a **console program** that **inputs the grade** (decimal number) and prints **Excellent!** if the grade is **5.50** or high.

[task]  
    [code-editor language=csharp]
        var grade = double.Parse(Console.ReadLine());
    [/code-editor]

    [task-description]
    [/task-description]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 6 | Excellent! |
| 5 | (no output) |
| 5.5 | Excellent! |
| 5.49 | (no output) |
[/slide]

[slide]
#### Create a new C # project

We create **a new project** in the existing Visual Studio solution. In **Solution Explorer**, right-click on **Solution 'Simple-Conditions'**. Then choose [**Add**] -> [**New Project**]:
 
[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/09.Excellent-result-01.png alt="New Console Project" /]

A dialog box will open for selecting a project. We choose **C # console application** and create a name, for example "Excellent-Result":
 
[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/09.Excellent-result-02.png alt="New Console Project" /]
 
Now we have a solution with one console application in it. It remains to write the code to solve the problem.
[/slide]

[slide]
#### Writing the code

For this purpose we go into the body of the **`Main (string [] args)`** method and write the following code:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/09.Excellent-result-03.png alt="Code" /]

**Run** the program with [**Ctrl+F5**], to test it with different input values:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/09.Excellent-result-04.png alt="Console" /]

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/09.Excellent-result-05.png alt="Console" /]

[/slide]

[slide]
#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#0]           
							https://judge.softuni.bg/Contests/Practice/Index/506#0
						 [/anchor].

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/09.Excellent-result-06.png alt="Judge System" /]

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/09.Excellent-result-07.png alt="Judge System" /]
[/slide]

[slide]
### Problem: excellent grade or not

The next exercise from this topic is to write a **console program** that **inputs the grade** (decimal number) and prints **Excellent!** if the rating is **5.50** or higher , otherwise "**Not excellent.**".

[task]  
    [code-editor language=csharp]
        var grade = double.Parse(Console.ReadLine());
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 6 | Excellent! |
| 5 | Not excellent. |
| 5.5 | Excellent! |
| 5.49 | Not excellent. |
[/slide]

[slide]
#### Create a new C # project

First we create **a new C# console project** in the **Simple-Conditions** solution.

  - We click on the solution in Solution Explorer and choose [**Add**] -> [**New Project**].
 
  - We choose [**Visual C#**] -> [**Windows**] -> [**Console Application**] and create a name, for example: “Excellent-or-Not”.
 
Now we have to **write the code** of the program. We can help with the sample code from the picture:  

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/02.Excellent-or-not-01.png alt="Code" /]
[/slide]

[slide]
#### Auto set startup the project

We turn on mode to **automatic switching to the current project** by clicking on the main Solution with the right mouse button and choosing [**Set StartUp Projects...**]:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/02.Excellent-or-not-02.png alt="Set Startup Project" /]


A dialog box will appear and you have to choose [**Startup Project**] -> [**Current selection**]:
 
[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/02.Excellent-or-not-03.png alt="Set Startup Project" /]
[/slide]

[slide]
#### Test the app

Now **we run the program** as usual with [**Ctrl + F5**] and test it if it works correctly:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/02.Excellent-or-not-04.png alt="Console" /]
[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/02.Excellent-or-not-05.png alt="Console" /]

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#1]           
							https://judge.softuni.bg/Contests/Practice/Index/506#1
						 [/anchor].

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/02.Excellent-or-not-06.png alt="Judge System" /]
[/slide]

[slide]
### Problem: even or odd

Write a program that checks whether an **integer** is **even** or **odd**.

[task]  
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
        Checking if the given number is even can be done with the operator **`%`**.
    [/task-description]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 2 | even |
| 3 | odd |
| 25 | odd |
| 1024 | even |

#### Hints and Guidelines

Again, first we add **a new C # console project** in the existing solution. In the **`static void Main ()`** method, we have to write the program code. Checking if the given number is even can be done with the operator **`%`**, which will return the **remainder from an integer divided by 2** as follows: **`var isEven = (num % 2 == 0)`**.

Now we **run** the program with [**Ctrl + F5**] and test it:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/03.Even-or-odd-01.png alt="Console" /]

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#2]           
							https://judge.softuni.bg/Contests/Practice/Index/506#2
						 [/anchor].
[/slide]

[slide]
### Problem: Greater number

Write a program that inputs **two integers** and prints the larger one.

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
|-----|------|
|5<br>3| 5 |
|3<br>5| 5 |
|10<br>10| 10 |
|-5<br>5| 5 |

#### Hints and Guidelines

As usual, first we need to add a **new C # console project** to the existing solution. For the code of the program we need a single **`if-else`** construction. You can partially help with the code from the picture that is deliberately blurred to think about how to write it yourself:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/04.Greater-number-02.png alt="Code" /]

When we are done with the implementation of the solution, we **run** the program with [**Ctrl + F5**] and test it:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/04.Greater-number-01.png alt="Console" /]

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#3]           
							https://judge.softuni.bg/Contests/Practice/Index/506#3
						 [/anchor].
[/slide]

[slide]
### Problem: digit in english

Write a program that inputs **an integer in the range** [**0 ... 9**] and output it **with words** in English. If the number is out of range, print "**too large a number**".

[task]  
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
        You can use a series of **`if-else`** conditions to create the possible **11 cases**.
    [/task-description]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 5 | five |
| 1 | one |
| 9 | nine |
| 10 | number too big |

#### Hints and Guidelines

We can use a series of **`if-else`** conditions to create the possible **11 cases**.

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#4]           
							https://judge.softuni.bg/Contests/Practice/Index/506#4
						 [/anchor].
[/slide]

[slide]
### Problem: guess the password

Write a program that **inputs a password** (one line with random text) and checks if the input **matches** with the phrase "**s3cr3t! P @ ssw0rd**". If it matches, print "**Welcome**", otherwise "**Wrong password!**".

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| qwerty | Wrong password! |
| s3cr3t!P@ssw0rd | Welcome |
| s3cr3t!p@ss | Wrong password! |

#### Hints and Guidelines

Use the **`if-else`** construction.

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#8]           
							https://judge.softuni.bg/Contests/Practice/Index/506#8
						 [/anchor].
[/slide]

[slide]
### Problem: number from 100 to 200

Write a program that **inputs an integer** and checks if it is **below 100**, **between 100 and 200** or **over 200**. Print the appropriate message as in the examples below.

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 95 | Less than 100 |
| 120 | Between 100 and 200 |
| 210 | Greater than 200 |

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#9]           
							https://judge.softuni.bg/Contests/Practice/Index/506#9
						 [/anchor].
[/slide]

[slide]
### Problem: equal words

Write a program that **inputs two words** and checks if they are the same. Do not make difference between uppercase and lowercase letters. You have to print "**yes**" or "**no**".

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| Hello<br>Hello | yes |
| SoftUni<br>softuni | yes |
| Soft<br>Uni | no |
| beer<br>vodka | no |
| HeLlO<br>hELLo | yes |

#### Hints and Guidelines

Before comparing the words, turn them to a lowercase to avoid the letter size influence (uppercase / lowercase): **`word = word.ToLower()`**.

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#10]           
							https://judge.softuni.bg/Contests/Practice/Index/506#10
						 [/anchor].
[/slide]

[slide]
### Problem: speed info

Write a program that **inputs the speed** (decimal number) and prints **speed information**. For speed **up to 10** (inclusive), print "**slow**". For speed **over 10** and **up to 50**, print "**average**". For speed **over 50 and up to 150**, print "**fast**". For speed **over 150 and up to 1000**, print "**ultra fast**". For higher speed, print "**extremely fast**".

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 8 | slow |
| 49.5 | average |
| 126 | fast |
| 160 | ultra fast |
| 3500 | extremely fast |

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#11]           
							https://judge.softuni.bg/Contests/Practice/Index/506#11
						 [/anchor].
[/slide]

[slide]
### Problem: area of figures

Write a program that ** inputs the sizes of a geometric figure** and **calculates its face**. The figures are four types: **square**, **rectangle**, **circle** and **triangle**.

The first line of the entrance reads the type of the figure (`square`, `rectangle`, `circle`, `triangle`).
* If the figure is **square**, the next row reads one number - the length of its side.
* If the figure is a **rectangle**, on the next two rows we read two numbers - the lengths of its sides.
* If the figure is **circle**, the next row reads one number - the radius of the circle.
* If the figure is **triangle**, on the next two rows we read two numbers - the length of the side and the length of its height.

Round the result up to the **third digit after the decimal point**.

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| square<br>5 | 25 |
| rectangle<br>7<br>2.5 | 17.5 |
| circle<br>6 | 113.097 |
| triangle<br>4.5<br>20 | 45 |

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#12]           
							https://judge.softuni.bg/Contests/Practice/Index/506#12
						 [/anchor].
[/slide]

[slide]
### Problem: time plus 15 minutes

Write a program that **inputs hours and minutes** from a 24-hour day and calculates how much it will be **after 15 minutes**. Print the result in **hh: mm** format. Hours are always between 0 and 23, and minutes are always between 0 and 59. Hours are written with one or two digits. Minutes are always written with two digits and zero at the front when needed.

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 1<br>46 | 2:01 |
| 0<br>01 | 0:16 |
| 23<br>59 | 0:14 |
| 11<br>08 | 11:23 |
| 12<br>49 | 13:04 |

#### Hints and Guidelines

Add 15 minutes and write a few conditions. If minutes are over 59, **increase hours** with 1 and **reduce minutes** with 60. Thereby look at the case when hours are over 23. When you print the minutes you should **check for zero at the front**.

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#13]           
							https://judge.softuni.bg/Contests/Practice/Index/506#13
						 [/anchor].
[/slide]

[slide]
### Problem: equal numbers

Write a program that inputs **3 numbers** and prints whether they are the same (**yes** / **no**).

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 5<br>5<br>5 | yes |
| 5<br>4<br>5 | no |
| 1<br>2<br>3 | no |

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#14]           
							https://judge.softuni.bg/Contests/Practice/Index/506#14
						 [/anchor].
[/slide]

[slide]
### Problem: \* number to words

Write a program that converts a number in the range of [**0 ... 100**] into text.

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

#### Sample Input and Output

| Input | Output |
| --- | ---- |
| 25 | twenty five |
| 42 | forty two |
| 6  | six |

#### Hints and Guidelines

First check for **one-digit numbers** and if the number is one-digit, print the appropriate word for it. Then check for **two-digit numbers**. Print them in two parts: left part (**tenth** = number / 10) and right part (**units** = number % 10). If the number has 3 digits, it must be 100 and can be considered as a special case.

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/506#15]           
							https://judge.softuni.bg/Contests/Practice/Index/506#15
						 [/anchor].

[/slide]

[slide]
## Graphical (desktop) application: currency converter

After we've done some exercises on **conditional statements (checks)**, now let's do something more interesting: an application with a graphical user interface for converting currencies. We will use the knowledge from this chapter to choose from several available currencies and make calculations at different rate to the selected currency.

Now let's see how to create a graphical (**GUI**) app for **currency conversion**. The app will look like the picture below:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/14.Converter-01.png alt="Currency Converter" /]
[/slide]

[slide]
#### Create a new C # project and add controls

This time we create a new **Windows Forms Application** with name “Currency-Converter”:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/14.Converter-02.png alt="New Project" /]

**We order the following controls** in the form:
* One box for entering a number (**`NumericUpDown`**)
* One drop-down list with currencies (**`ComboBox`**)
* Text block for the result (**`Label`**) 
* Several inscriptions (**`Label`**)

We set the **sizes** and their properties to look like the picture below:
 
[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/14.Converter-03.png alt="Controls" /]
[/slide]

[slide]
#### Configuring the controls

We set the **configuring controls**:

* **For the main form** (**`Form`**), that contains all the controls:
  * **`(name)`** = **`FormConverter`**
  * **`Text`** = "**`Currency Converter`**"
  * **`Font.Size`** = **`12`**
  * **`MaximizeBox`** = **`False`**
  * **`MinimizeBox`** = **`False`**
  * **`FormBorderStyle`** = **`FixedSingle`**
<br>

* For the **field for entering a number** (**`NumericUpDown`**):
  * **`(name)`** = **`numericUpDownAmount`**
  * **`Value`** = **`1`**
  * **`Minimum`** = **`0`**
  * **`Maximum`** = **`1000000`**
  * **`TextAlign`** = **`Right`**
  * **`DecimalPlaces`** = **`2`**
<br>  

* For the **drop-down list with currencies** (**`ComboBox`**):
  * **`(name)`** = **`comboBoxCurrency`**
  * **`DropDownStyle`** = **`DropDownList`**
  * **`Items`** =
    * **EUR**
    * **USD**
    * **GBP**
<br> 

* For the **result text block** (**`Label`**):
  * **`(name)`** = **`labelResult`**
  * **`AutoSize`** = **`False`**
  * **`BackColor`** = **`PaleGreen`**
  * **`TextAlign`** = **`MiddleCenter`**
  * **`Font.Size`** = **`14`**
  * **`Font.Bold`** = **`True`**
[/slide]

[slide]
#### Events and eventhandlers

We need to take the following **events** to write the C # code that will be executed upon their occurrence:

* The Event **`ValueChanged`** of numeric entry control **`numericUpDownAmount`**:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-3-images/14.Converter-04.png alt="Events" /]

* The event **`Load`** of the form **`FormConverter`**
* The event **`SelectedIndexChanged`** of the drop-down list for choosing the currency **`comboBoxCurrency`**
  
We will use the following **C# code** for event handling:

```csharp
private void FormConverter_Load(object sender, EventArgs e)
{
  this.comboBoxCurrency.SelectedItem = "EUR";
}
        
private void numericUpDownAmount_ValueChanged(object sender, EventArgs e)
{
  ConvertCurrency();
}
        
private void comboBoxCurrency_SelectedIndexChanged(object sender, EventArgs e)
{
  ConvertCurrency();
}
```

Our task is to select the currency "**EUR**" when we start the program and change the values in the sum or currency field then calculate the result by calling the **`ConvertCurrency()`** method.
[/slide]

[slide]
#### Writing the code

We have to write the event **`ConvertCurrency()`** to convert the amount of levs in the selected currency:

```csharp
private void ConvertCurrency()
{
  var originalAmount = this.numericUpDownAmount.Value;
  var convertedAmount = originalAmount;
  if (this.comboBoxCurrency.SelectedItem.ToString() == "EUR")
      {
        convertedAmount = originalAmount / 1.95583m;
      }
  else if (this.comboBoxCurrency.SelectedItem.ToString() == "USD")
      {
        convertedAmount = originalAmount / 1.80810m;
      }
  else if (this.comboBoxCurrency.SelectedItem.ToString() == "GBP")
      {
        convertedAmount = originalAmount / 2.54990m;
      }
  this.labelResult.Text = originalAmount + " лв. = " +
  Math.Round(convertedAmount, 2) + " " + this.comboBoxCurrency.SelectedItem;
}
```

The above code takes **the amount** for convert from the field **`numericUpDownAmount`** and **the selected currency** for the result from the field **`comboBoxCurrency`**. Then with a **conditional statement**, according to the selected currency, the amount is divided by **the exchange rate** (which is fixed in the source code). Finally, a text **message with the result** (rounded to second digit after the decimal point) is generated and recorded in the green box **`labelResult`**. Try it!

If you have problems with the example above, **watch the video** at the beginning of this chapter or ask in the [anchor href=https://softuni.bg/forum]**forum of SoftUni**[/anchor].
[/slide]