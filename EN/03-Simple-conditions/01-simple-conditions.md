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

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]

[slide]

[/slide]