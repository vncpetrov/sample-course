[slide]
# Chapter 2.1. Simple Calculations

In this chapter we are going to get familiar with the following concepts and programming techniques: 

- What is the **system console**?
- How to **read numbers** from the system console?
- How to work with **data types and variables**, which are necessary to process numbers and the operations between them?
- How to **print** a result (a number) on the console?
- How to do simple **arithmetic operations**:  add, substract, multiply, divide, string concatenation?

## Video

[youtube-video videoId=0f7c9RIZGaE /]
[/slide]

[slide]
## System Console 

Simply called "**console**", the system, also the computer console, represents the tool by which we give the computer commands in a text format and receive the results from their execution again as a text. 

Generally the system console represents a text terminal, which means that it accpets and visualizes just **text** without any graphical elements like buttons, menus, etc. It usually looks like a black coloured window like this one: 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Console-example.png 
       alt="Console" /]

In most operating systems, the **console** is available as a standalone application on which we write console commands. It is called a **Command Prompt** in Windows, and in Linux and Mac a **Terminal**. The console runs console applications. They read text from the command line and print text on the console. In this book we are going to learn programming mostly through creating **console applications**.
[/slide]

[slide]
## Reading Integers From The Console

In order to read an **integer** (not a float) **number** from the console, we have to **declare a variable**, declare the **number type** and use the standart command for reading information from the system console: 

```csharp
var num = int.Parse(Console.ReadLine());
```
[/slide]

[slide]
### Example: calculating a square area with side **а**

For example, let us look at the following program, which reads an integer from the console, multiplies it by itself (squares it) and prints the result from the multiplication. This way we can calculate the square area by the given length of the side:

```csharp
Console.Write("a = ");              
var a = int.Parse(Console.ReadLine());
var area = a * a;
Console.Write("Square area = ");
Console.WriteLine(area);
```

Here is how the program would work when we have a square with a side length equal to 3:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Square-area-01.jpg 
       alt="Console" /]

Try to write a wrong number, for example "**hello**". You will receive an error message during runtime (exception). This is normal. Later on, we will find out how we can catch this kinds of errors and make the user enter a number again. 

#### Testing in the Judge system

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#0]           
                            dge.softuni.bg/Contests/Practice/Index/504#0
                         [/anchor].
[/slide]

[slide]
#### How does the example work?

The first row **`Console.Write("a = ");`** prints an informative message, which invites the user to enter the side of the square  **a**. After the output is printed, the cursor stays on the same row. Staying on the same row is more convinient for the user, visually. We use **`Console.Write(…)`**, and not **`Console.WriteLine(…)`** and this way the cursor stays on the same row.

The next row **`var a = int.Parse(Console.ReadLine());`** reads an integer from the console. Actually, it reads a text first (string) using **`Console.ReadLine()`** and after that it gets converted to an integer (it is parsed) using **`int.Parse(…)`**. The result is kept in a variable with name **`a`**.

The next command **`var area = a * a;`** keeps in a new variable **`area`** the result of the multiplication of **`a`** by **`a`**.

The next command **`Console.Write("Square area = ");`** prints the given text without goint to the next line. Again, it is used  **`Console.Write(…)`**, and not **`Console.WriteLine(…)`** and this way the cursor stays on the same row in order to print the calculated area of the square afterwards. 

The last command **`Console.WriteLine(area);`** prints the calculated value of the variable  **`area`**.
[/slide]

[slide]
## Calculations in Programming

We know that computers are machines that process data. All **data** is stored inside the computer memory (RAM) in **variables**. The variables are named areas in the memory, which keep a certain data type, for example a number or a text. Each of the **variables** in C# has a **name**, a **type** and a **value**. Here is how we would declare a variable and assign it with a value at the same time: 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Declaring-variables-01.png 
       alt="Declaring Variables" /]

After being processed, data is again stored  in variables (in somе place in the memory saved for our program).
[/slide]

[slide]
## Data Types and Variables

In programming, every variable keeps a certain **value** of some **type**. For example, data types can be: **number**, **letter**, **text** (string), **data**, **colour**, **picture**, **list** and others.
Here are some examples for data types:
- type **integer**: 1, 2, 3, 4, 5, …
- type **float**: 0.5, 3.14, -1.5, …
- type **character** (symbol): 'a', 'b', 'c', …
- type **text** (string): "Hello", "Hi", "Beer", …
- type **day of week**: Monday, Tuesday, …
[/slide]

[slide]
## Reading Floating-Point Numbers From the Console

To read a **real number** from the console, it is necessary to а **declare a variable** again, define its **numeric type**, and also use the standart command for reading information from the console:

```csharp
var num = double.Parse(Console.ReadLine());
``` 
[/slide]

[slide]
### Example: converting inches to centimeters

Let us write a program, which reads a floating-point number in inches and converts it to centimeters:

```csharp
Console.Write("Inches = ");              
var inches = double.Parse(Console.ReadLine());
var centimeters = inches * 2.54;
Console.Write("Centimeters = ");
Console.WriteLine(centimeters);
```

Let us start the program and make sure that when a value in inches is entered, we receive a correct answer in centimeters:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Inches-to-centimeters-01.jpg 
       alt="Code" /] 

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#1]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#1
                         [/anchor].
[/slide]

[slide]
## Reading a Text

To read a text (string) from the console, again, we have to **declare a new variable** and use the standart  **command for reading information from the console**:

```csharp
var str = Console.ReadLine();
```

Let us pay attention to the fact that the **reading of  text is not declared** in any way as a type "**`string`**" (text). The reason is because by default the  **`Console.ReadLine(…)`** method returns a **text result**. Additionally, you can parse the text to an integer by **`int.Parse(…)`** or a real number by **`double.Parse(…)`**. If this is not done, for the program **every number** will be just **text**, and we **cannot do** arithmetic operations with it.
[/slide]

[slide]
### Example: greeting by name

Let us write a program that asks the user for his name and salutes him with the text "**Hello, *name***".

```csharp           
var name = Console.ReadLine();
Console.WriteLine("Hello, {0}!", name);
```

In this case **`{0}`** is replaced with the **first** given argument, which holds the variable **`name`**:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Greeting-by-name-01.jpg 
       alt="Console" /]  

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#2]           
                        https://judge.softuni.bg/Contests/Practice/Index/504#2
                        [/anchor].
[/slide]

[slide]
## Printing Text and Numbers

When printing a text, numbers and other data on the console,  **we can join them** by using templates **`{0}`**, **`{1}`**, **`{2}`** etc. In programming, these templates are called **placeholders**.

```csharp
var firstName = Console.ReadLine();
var lastName = Console.ReadLine();
var age = int.Parse(Console.ReadLine());
var town = Console.ReadLine();
Console.WriteLine("You are {0} {1}, a {2}-years old person from {3}.",
firstName, lastName, age, town);
```

Here is the result we are going to receive after the execution of this example: 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Placeholders-01.jpg 
       alt="Console" /]

Notice how every variable should be given in the **order, in which we want it to be printed**. Practically, the template (**placeholder**) **accepts variables from every type**.

It is possible for a template to be used multiple times and it is not necessary for the templates to be numbered sequentially. Here is an example:

```csharp
Console.WriteLine("{1} + {1} = {0}", 1+1, 1);
```

The result is:

```
1 + 1 = 2
```

### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#3]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#3
                         [/anchor].
[/slide]

[slide]
## Arithmetic Operations

Let us look at the basic arithmetic operations in programming.

### Addition of Numbers (operator **`+`**)

We can add a number with the operator **`+`**:

```csharp
var a = 5;
var b = 7;
var sum = a + b; // the result is 12
``` 

### Substraction of Numbers (operator **`-`**)

Substracting a number is done by the operator **`-`**:

```csharp
var a = int.Parse(Console.ReadLine());
var b = int.Parse(Console.ReadLine());
var result = a - b;
Console.WriteLine(result);
```

Here is the result from the execution of this program (with numbers 10 and 3):

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Subtracting-01.jpg 
       alt="Console" /] 

### Multiplication of Numbers (operator **`*`**)

For multiplication of numbers we use the operator **`*`**:

```csharp
var a = 5;
var b = 7;
var product = a * b; // 35
```
[/slide]

[slide]
### Division of Numbers (operator /)

Dividing numbers is done by the operator **`/`**. It works differently with integers and floating-point numbers.
* When we divide two whole numbers, an **integer divison** is applied and the received output is without its fractional part. Example: 11 / 3 = 3.
* When we divide two numbers and at least one of them is a real number, a **floating division** is applied and the received result is a real number, just as it is in math. Example 11 / 4.0 = 2.75.  When it cannot be done with exact precision, the result is being rounded, for example 11.0 / 3 = 3.66666666666667.
* The integer **division by 0** causes  an **exception** during runtime (runtime exception).
* Real numbers **divided by 0** do not cause an exception and the result is  **+/- infinity** or a special value  **NaN**. Example 5 / 0.0 = &#8734;.

Here are a few examples with the divison operator:

```csharp
var a = 25;
var i = a / 4;      // we are applying an integer division:
                    // the result of this operation will be 6 – the fractional part will be cut, 
                    // because we are dividing integers
var f = a / 4.0;    // 6.25 – floating division. We have set the number 4 to be interpreted 
                    // as a float by adding a decimal separator followed by zero 
var error = a / 0;  // Error: Integer divide by zero
```

Let us look at a few examples for **integer division** (remember that when we **divide integers** in C# the result is a **whole number**):

```csharp
var a = 25;
Console.WriteLine(a / 4);  // Integer result: 6
Console.WriteLine(a / 0);  // Error: divide by 0
```

Let us look at a few examples for **floating division**. When we divide floating-point numbers, the result is always a **real number** and the division never fails and works correct with the special values **+&#8734;** and **-&#8734;**:

```csharp
var a = 15;
Console.WriteLine(a / 2.0);    // Float result: 7.5
Console.WriteLine(a / 0.0);    // Result: Infinity
Console.WriteLine(-a / 0.0);   // Result: -Infinity
Console.WriteLine(0.0 / 0.0);  // Result: NaN (Not a Number), e.g. the result
                               // from the operation is not a valid numeric value
```

When printing the values  **&#8734;** and **-&#8734;**, the console output may be `?`, because the console in Windows does not work correctly with Unicode and breaks most of the non-standart symbols, letters and special signs. The example above would most probably give the following result:

```
7.5
?
-?
NaN
```
[/slide]

[slide]
## Concatenating a Text and a Number

Except for addition of numbers, the operator **`+`** is used for joining a text (concatenation of two strings one after another). In programming, joining a text with a text is called "**concatenation**". Here is how we can concatenate a text with a number by the **`+`** operator:

```csharp
var firstName = "Maria";
var lastName = "Ivanova";
var age = 19;
var str = firstName + " " + lastName + " @ " + age;
Console.WriteLine(str);  // Maria Ivanova @ 19
```

Here is another example:

```csharp
var a = 1.5;
var b = 2.5;
var sum = "The sum is: " + a + b;
Console.WriteLine(sum);  // The sum is: 1.52.5
```

Did you notice something strange? May be you expecteded the numbers **`a`** and  **`b`** to be summed? Actually the concatenation works from rigth to left and the result above is absolutely correct. If we want to sum the numbers, we have to use **brackets**, in order to change the order of execution of the operations:

```csharp
var a = 1.5;
var b = 2.5;
var sum = "The sum is: " + (a + b);
Console.WriteLine(sum);  // The sum is: 4
``` 
[/slide]

[slide]
## Numerical Expressions

In programming, we can calculate **numerical expressions**, for example:

```csharp
var expr = (3 + 5) * (4 – 2);
```

The standart rule for priorities of the arithmetic operations is applied: **multiplying and dividing are always done before adding and substracting**. In case of an **expression in brackets, it is calculated first**, but we already know all of that from school math.
[/slide]

[slide]
### Example: calculating a trapezoid area

Let us write a program that takes the lengths of the two bases of a trapezoid and its height (one floating-point number per row) and calculates the **area of the trapezoid** by the standart math formula: 

```csharp
var b1 = double.Parse(Console.ReadLine());
var b2 = double.Parse(Console.ReadLine());
var h = double.Parse(Console.ReadLine());
var area = (b1 + b2) * h / 2.0;
Console.WriteLine("Trapezoid area = " + area);
```

If we start the program and enter values for the sides 3, 4 and 5, we will receive the following result:

```
3
4
5
Trapezoid area = 17.5
```

#### Testing in the Judge System

Test your solution here : [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#4]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#4
                          [/anchor].
[/slide]

[slide]
### Example: perimeter and area of a circle

Let us write a program that calculates  **a circle area and a perimeter** by reading its **radius r** .

Formulas:
- Area = π \* r \* r
- Perimeter = 2 \* π \* r
- π ≈ 3.14159265358979323846…

```csharp
Console.Write("Enter circle radius. r = ");
var r = double.Parse(Console.ReadLine());
Console.WriteLine("Area = " + Math.PI * r * r); 
// Math.PI - built in constant for π in C#
Console.WriteLine("Perimeter = " + 2 * Math.PI * r);
```
Let us test the program with **radius `r = 10`**:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Circle-area-01.jpg 
       alt="Console" /] 

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#5]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#5
                         [/anchor].
[/slide]

[slide]
### Example: area of a rectangle on a coordinate plane

There is a given rectangle with the **coordinates of two of its opposite angles**. Calculate the  **area and its perimeter**:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Rectangle-area-01.png 
       alt="Console" /]

In this task, we have to consider that if we substract the smaller `x` from the bigger `x`, we will receive the length of the rectangle. Analogically, if we substract the smaller `y` from the bigger `y` , we will receive the height of the rectangle. What is left is to multiply both sides. Here is an example of an implementation of the described logic: 

```csharp
var x1 = double.Parse(Console.ReadLine());
var y1 = double.Parse(Console.ReadLine());
var x2 = double.Parse(Console.ReadLine());
var y2 = double.Parse(Console.ReadLine());

// Calculating the sides of the rectangle:
var width = Math.Max(x1, x2) - Math.Min(x1, x2);
var height = Math.Max(y1, y2) - Math.Min(y1, y2);

Console.WriteLine("Area = " + width * height);
Console.WriteLine("Perimeter = " + 2 * (width + height));
```

We use **`Math.Max(a, b)`**, to find the bigger value **`a`** and **`b`** and analogically **`Math.Min(a, b)`** to find the smaller of both values. 

When the program is executed with the values from the coordinate system given in the condition, we receive the following result:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Rectangle-area-02.jpg 
       alt="Console" /]

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#6]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#6
                         [/anchor].
[/slide]

[slide]
## What did we learn from this chapter?

Let us summarize what we learned in this chapter of the book:

- **Inserting a text**: **`var str = Console.ReadLine();`**.
- **Inserting a whole number**: **`var num = int.Parse(Console.ReadLine());`**.
- **Inserting a real number**: **`var num = double.Parse(Console.ReadLine());`**.
- **Calculations with numbers** and using the suitable  **arithmetic operators** [+, -, \*, /, ()]: **`var sum = 5 + 3;`**.
- **Printing a text by placeholders** on the console: **`Console.WriteLine("{0} + {1} = {2}", 3, 5, 3 + 5);`**.
[/slide]

[slide]
## Exercises: simple calculations

Let us confirm the knowledge gained througout this chapter with a few more exercises.

### Empty (Blank) Visual Studio Solution

We start by creating an empty solution **(Blank Solution)** in Visual Studio. The solutions in Visual Studio combine **a group of projects**. This opportunity is **very convenient**, when we want to **work on a few projects** and switch quickly between them or we want to **unite logically a few interconnected projects**.
In the current practical exercise we will use a **Blank Solution with a couple of projects** to organize the solutions of the tasks from the exercises - every task in a separate project and all of them in a common solution.

*	We start Visual Studio
* We create a new **Blank Solution:** [**File**] -> [**New**] -> [**Project**].

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Blank-solution-01.png
       alt="Visual Studio" /] 

We choose from the dialogue window [**Templates**] -> [**Other Project Types**] -> [**Visual Studio Solutions**] -> [**Blank Solution**] and we give an appropriate name of the project, for example “Simple-Calculations”:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Blank-solution-02.png
       alt="Visual Studio" /]

Now we have created and **emply Visual Studio Solution** (with 0 projects in it):

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/00.Blank-solution-03.png
       alt="Visual Studio" /]

The purpose of this blank solution is to add **a project per problem** from the exercises.
[/slide]

[slide]
### Problem: calculating the area of a square

The first exercise from this theme is the following : write a console program that  **reads a whole number `a` and calculates the area** of a square with side **`a`**. The task is trivial and easy: **read a number** from the console, **multiply it by itself** and **print the received result** on the console.

[task]
    [code-editor language=csharp]
        Console.Write("a = ");
        var a = int.Parse(Console.ReadLine());
        var area = ...

        // TODO: Calculate and print the area
    [/code-editor]
[/task]

#### Hints and Guideliness

We create a **new project** in the existing Visual Studio Solution. In the **Solution Explorer** click the right button of the mouse on **Solution 'Simple-Calculations'**. Choose [**Add**] -> [**New Project…**]:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/01.Square-area-01.png 
       alt="Visual Studio" /]

**A dialogue window** is going to be opened for a choice of **project type** for creation. We choose **C# console application** with name “Square-Area”:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/01.Square-area-02.png 
       alt="Visual Studio" /]

We already have a solution with one console application in it. It is left to write the **code for solving this problem**.  For this purpose we go to the main method's body **`Main(string[] args)`** and write the following code:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/01.Square-area-03.png 
       alt="Code" /]

The code enters a whole number through **`a = int.Parse(Console.ReadLine())`**, afterwards it calculates  **`area = a * a`** and finally prints the value of the variable **`area`**. **We start** the program with [**Ctrl+F5**] and **test** it with different input values: 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/01.Square-area-04.png 
       alt="Console" /]
[/slide]

[slide]
#### Tetsing in the Judge System

Test your solution here:  [https://judge.softuni.bg/Contests/Practice/Index/504#0](https://judge.softuni.bg/Contests/Practice/Index/504#0). You have to receive  100 points (completely correct solution):

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/01.Square-area-05.png 
       alt="Judge System" /]

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/01.Square-area-06.png 
       alt="Judge System" /] 
[/slid e]

[slide]
### Exercies: from inches to centimeters

Write a program that **reads a number from the console** (it is not mandatory to be a whole number) and converts the number from **inches to centimeters.** For the purpose **it multiplies the inches by  2.54** (because one inch = 2.54 centimeters).

[task]
    [code-editor language=csharp]
        Console.Write("Inches = ");
        var inches = double.Parse(Console.ReadLine());

        // TODO: Calculate and print centimeters
    [/code-editor]
[/task]

#### Hints and Guideliness

First, we create a **new C# console project** in the solution  “Simple-Calculations”. We click the mouse's right button on the solution in the **Solution Explorer** and we choose [**Add**] -> [**New Project…**]:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-01.png 
       alt="New Project" /] 

Choose [**Visual C#**] -> [**Windows**] -> [**Console Application**] and name it “Inches-to-Centimeters”:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-02.png 
       alt="New Project" /] 
[/slide]

[slide]
#### Writing the program code and starting the program

Next, we have to write the **program code**:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-03.png 
       alt="Code" /] 

**Start the program** with [**Ctrl+F5**]:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-04.png 
       alt="Console" /] 

Surprise! What is happening? The program doesn't work correctly… Actually, isn't this the previous program?
In Visual Studio **the current active project** in a solution is marked in half black colour and it could be changed:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-05.png 
       alt="Solution Explorer" /] 
[/slide]

[slide]
#### Setting up a startup project

To switch the mode to **automatically go to current project**, we click on the main solution with the mouse's right button and we choose [**Set StartUp Projects…**]:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-06.png 
       alt="Set Startup Project" /] 

A dialogue window will open and you will have to choose from it [**Startup Project**] -> [**Current Selection**]:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-07.png 
       alt="Set Startup Project" /] 

And again,  **we run the program**, as usual with [**Ctrl+F5**]. This time it will start **the current open program**, which converts inches to centimeters. It looks like it works correctly:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-08.png 
       alt="Console" /] 
[/slide]

[slide]
#### Switching between programs

Now **lets switch on the previous program** (square area). This happens with a double mouse click  on the file **``Program.cs``** from the previous project **“Square-Area”** in the panel [**Solution Explorer**] of Visual Studio:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-12.png 
       alt="Visual Studio" /] 

We press again [**Ctrl+F5**]. This time the other project should start:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-11.png 
       alt="Console" /] 

We switch back on the **“Inches-to-Centimeters”** project and start it with [**Ctrl+F5**]:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-09.png 
       alt="Console" /] 

**Switching between projects** is very easy, isn't it? Just choose the file with the source code of the program, double click it with the mouse and when it starts, the program from the current file is being executed.  
[/slide]

[slide]
#### Testing the program locally 

Let us test with floating-point numbers, for example with **2.5**:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-10.png 
       alt="Console" /] 

<table><tr><td><img src="https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/alert-icon.png" style="max-width:50px" /></td>
<td>Depending on the regional settings of the operational system, it is possible instead of using a <b>decimal point </b> (US settings), to be used a <b>decimal comma</b> (BG settings).</td>
</tr></table>

If the program expects a decimal point and instead a number with a decimal comma is entered or the opposite (to enter a decimal point, when a decimal comma is expected), the following error will be received:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-13.png 
       alt="Console" /] 

It is recomended to **change the settings of our computer** to use a **decimal point**:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-14.png 
       alt="Region Settings" /] 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-15.png 
       alt="Region Settings" /] 
[/slide]

[slide]
#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#1]           
                                https://judge.softuni.bg/Contests/Practice/Index/504#1
                            [/anchor].

The solution should be received as a completely correct one:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/02.Inches-to-centimeters-16.png 
       alt="Judge System" /] 
[/slide]

[slide]
### Problem: greeting by name

Write a program that  **reads a person's  name** and prints **`Hello, <name>!`**, where **`<name>`** is the name entered earlier.

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]

#### Hints and Guideliness

First, we create a **new C# console project** with name “Greeting” in the solution “Simple-Calculations”:

    [image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/03.Greeting-by-name-01.png 
           alt="Visual Studio" /] 

**Next we have to write the code** of the program. If you feel any difficulties, you can use the code from the example below:

    [image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/03.Greeting-by-name-02.png 
        alt="Visual Studio" /] 


**Run** the program with [**Ctrl+F5**] and test if it works:

    [image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/03.Greeting-by-name-03.png 
           alt="Console" /] 


#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#2]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#2
                         [/anchor].

[/slide]

[slide]
### Problem: concatenation of text and numbers

Write a C# program, that reads a name, a last name, an age and a city from the console and prints a message of the following kind: **`You are <firstName> <lastName>, a <age>-years old person from <town>`**.

[task]  
    [code-editor language=csharp]
    [/code-editor]
    
    [task-description]
        Message should be in the following format: **`You are <firstName> <lastName>, a <age>-years old person from <town>`
    [/task-description]
[/task]

#### Hints and Guideliness

We add to the exististing Visual Studio solution one more console C# project with name “Concatenate-Data”.	We **write the code** which reads the input from the console:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/04.Concatenate-data-01.png 
        alt="Code" /]


**The code** which prints the described in the condition of the problem message should be finished.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/04.Concatenate-data-02.png 
        alt="Code" /]

In the picture above the code is blurred on purpose, in order for you to think of a way to finish it yourself.

Next, the solution should be tested locally with [**Ctrl+F5**] and by entering an exemplary input data.

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#3]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#3
                         [/anchor].
[/slide]

[slide]
### Problem: trapezoid area

Write a program that reads three numbers from the console **b1, b2 and h and calculates the area of a trapezoid** with bases **b1 and b2 and height h. The formula for trapezoid area is  (b1 + b2) * h / 2**.

In the figure bellow is shown a trapezoid with bases 8 and 13 and height 7. It has an area **(8 + 13) * 7 / 2 = 73.5**.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/05.Trapezoid-area-01.png
       alt="Trapezoid" /]

[task]
    [code-editor language=csharp]
        var b1 = double.Parse(Console.ReadLine());
        // TODO: Calculate and print the area
    [/code-editor]

    [task-description]
        Multiplication in programming is performed by **`*`** operator.
    [/task-description]
[/task]

#### Hints and Guideliness

Again, we have to add to the existing Visual Studio solution another **console C# project** with name "Trapezoid-Area" and write the **code that reads the input from the console, calculates the trapezoid area and prints it**:
[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/05.Trapezoid-area-02.png
        alt="Code" /])

The code in the picture is purposely blurred, in order for you to give it a thought and finish it yourself.

**Test** your solution locally with [**Ctrl+F5**] and enter an examplary data.

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#4]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#4
                         [/anchor].

[/slide]

[slide]
### Problem: circle area and perimeter

Write a program that reads from the console a **number r** and calculates and prints **the circle's area and perimeter** with **radius r**.

[task]
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
            For the calculations you may use the following formulas: 
            -	**`Area = Math.PI * r * r`**.
            -	**`Perimeter = 2 * Math.PI * r`**.
    [/task-description]
[/task]

#### Input and output 

| Input  |           Output|    
|-----|--------------------------------------------------------|
| 3     | Area = 28.2743338823081 <br> Perimeter = 18.8495559215388|
| 4.5   | Area = 63.6172512351933 <br> Perimeter = 28.2743338823081|

#### Hints and Guideliness 



#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#5]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#5
                         [/anchor].
[/slide]

[slide]
### Problem: rectangle area in a coordinate plane

**A Rectangle** is given with the **coordinates** of both of its opposite angles (x1, y1) – (x2, y2). Calculate its  **area and perimeter**. **The input** is read from the console. The numbers **x1, y1, x2 and y2** are given one per line. **The output** is printed on the console and it has to contain two lines, each with one number - the area and the perimeter.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/07.Rectangle-area-01.png 
       alt="Rectangle Figure" /]

[task]
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
        **The output** is printed on the console and it has to contain two lines, each with one number - the area and the perimeter.
    [/task-description]
[/task]

#### Sample Input and Output

|               Input                        |       Output         |
|-----------------------------------------|-------------------|
|60<br>20<br>10<br>50                     |1500<br>160         |
|30<br>40<br>70<br>-10                   |2000<br>180         |
|600.25<br>500.75<br>100.50<br>-200.5    |350449.6875<br>2402 |

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#6]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#6
                         [/anchor].
[/slide]

[slide]
### Problem: triangle area

Write a program that reads from the console **a side and a height of a triangle** and calculates its area. Use the **formula** for triangle area: **area = a * h / 2**. Round the result to **2 digits after the decimal separator using `Math.Round(area, 2)`**.

[task]
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
        Use the **formula** for triangle area: **area = a * h / 2**.
    [/task-description]
[/task]

#### Sample Input and Output

|       Input           |         Output         |
|--------------------|---------------------|
| 20 <br>30            | Triangle area = 300   |
| 15 <br>35            | Triangle area = 262.5 |
| 7.75 <br>8.45        | Triangle area = 32.74 |
| 1.23456 <br>4.56789  | Triangle area = 2.82  |

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#7]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#7
                         [/anchor].
[/slide]

[slide]
### Problem: console converter - from degrees on °C to degrees on °F

Write a program that reads **degrees on Celsius scale** (°C) and converts them to **degrees on Fahrenheit** (°F). Look on the Internet for a proper [anchor href=http://bfy.tw/3rGh]formula[/anchor] to do the calculations. Round the result to **2 digits after the decimal separator**. Below are a few examples.

[task]
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
        Use the **formula** °F = °C × 1,8 + 32
    [/task-description]
[/task]

#### Sample Input and Output

| Input | Output |
|----|-----|
|  25  |   77  |
|   0  |   32  |
| -5.5 |  22.1 |
| 32.3 | 90.14 |

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#8]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#8
                         [/anchor].
[/slide]

[slide]
### Problem: console converter - from radians to degrees

Write a program, that reads **an angle in [anchor href=https://en.wikipedia.org/wiki/Radian]radians[/anchor]** (**`rad`**) and converts it to **[anchor href=https://en.wikipedia.org/wiki/Degree_(angle)]degrees[/anchor]** (**`deg`**). Look for a proper formula on the Internet. The number **π** in C# programs is available through **``Math.PI``**. Round the result to the nearest whole number using the **``Math.Round(…)``** method.

[task]
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
        The number **π** in C# programs is available through **``Math.PI``**.
    [/task-description]
[/task]

#### Sample Input and Output

|  Input  | Output |
|------|-----|
| 3.1416 |  180  |       
| 6.2832 |  360  | 
| 0.7854 |   45  | 
| 0.5236 |   30  |

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#9]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#9
                         [/anchor].
[/slide]

[slide]
### Problem: console converter - USD to BGN

Write a program for **conversion of US dollars** (USD) **in bulgarian levs** (BGN). **Round** the result to **2 digits** after the decimal separator. Use a fixed rate between a dollar and a lev: **1 USD = 1.79549 BGN**.

[task]
    [code-editor language=csharp]
    [/code-editor]

    [task-description]
        **1 USD = 1.79549 BGN**
    [/task-description]
[/task]

#### Sample Input and Output

|  Input  |    Output  |
|------|---------|
|   20   | 35.91 BGN |      
|   100  | 179.55 BGN|
|  12.5  | 22.44 BGN |

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#10]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#10
                         [/anchor].
[/slide]

[slide]
### Problem: \* console currency converter

Write a program for **conversion of money from one currency to another**. It has to maintain the following currencies: **BGN, USD, EUR, GBP**. Use the following fixed currency rates:

|  Курс  |   USD   |   EUR   |   GBP   |
|:------:|:-------:|:-------:|:-------:|
| 1 BGN  | 1.79549 | 1.95583 | 2.53405 |

**The input** is **sum for conversion**, **input currency** and **output currency**. **The output** is one number – the converted value of the above currency rates, rounded **2 digits** after the decimal point. 

[task]
    [code-editor language=csharp]
    [/code-editor]
[/task]

#### Sample Input and Output

|        Input        |   Output  |
|------------------|--------|
|   20<br>USD<br>BGN |35.91 BGN |     
|  100<br>BGN<br>EUR |51.13 EUR | 
| 12.35<br>EUR<br>GBP| 9.53 GBP |  
|150.35<br>USD<br>EUR|138.02 EUR|

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#11]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#11
                         [/anchor].
[/slide]

[slide]
### Problem: ** calcutations with dates - 1000 days on Earth

Write a program that enters Напишете програма, която въвежда **a birthdate** in format **`dd-MM-yyyy`** and calculates the date on which are turned и пресмята датата, на която се навършват **1000 days** from this birthdate and prints it in the same format.

[task]
    [code-editor language=csharp]
    [/code-editor]
[/task]

#### Sample Input and Output

|   Input   |	 Output  |
|--------|--------|
|25-02-1995|20-11-1997|
|07-11-2003|02-08-2006|
|30-12-2002|24-09-2005|
|01-01-2012|26-09-2014|
|14-06-1980|10-03-1983|

#### Hints and Guidelines 

* Look for information about the data type **``DateTime``** in C# and in particular look at the methods **``ParseExact(str, format)``**, **``AddDays(count)``** and **``ToString(format)``**. With their help you can solve the problem without the need to calculate days, months and leap years.
* **Don't print** anything additional on the console except for the wanted data!

#### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/504#12]           
                            https://judge.softuni.bg/Contests/Practice/Index/504#12
                         [/anchor].
[/slide]

[slide]
## Graphical Applications with Numerical Expressions

To exercise working with variables and calculations with operators and numerical expressions, we will make something interesting: we will develop a **desktop application** with graphical user interface. In it, we will use calculations with floating-point numbers.
[/slide]

[slide]
### Graphical application: converter from BGN to EUR

It is expected of us to create **a graphical application** (GUI application), which calculates the value in **euro** (EUR) of money amount, given in **leva** (BGN). By changing the amount in leva, the amount in euro has to recalculate itself automatically (we use rate leva / euro: **1.95583**).

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/13.Currency-converter-01.png 
       alt="BGN to EUR Converter App" /]

This exercise goes beyond the material learned in this book and its purpose is not to teach you how to program GUI applications, but to enlighten your interest in software development. Let's get to work.
[/slide]

[slide]
#### Creating a new C# project

We add to the existing Visual Studio solution one more project. This time we creatе **Windows Forms** application with C# named "BGN-to-EUR-Converter":

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/13.Currency-converter-02.png 
        alt="Create New Project" /]
[/slide]

[slide]
#### Adding controls

We arrange the following UI controls in the format: 

* **`NumericUpDown`** with name **`numericUpDownAmount`** – it will enter the amount for conversion
*	**`Label`** with name **`labelResult`** – it will show the result after conversion
*	Two more **`Label`** components, serving only for static representation of a text

The graphical editor for user interface might look similar to this:
[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/13.Currency-converter-03.png 
        alt="Graphical UI Editor" /] 

We set the following settings of the format and the separate controls:

|                                             Setting                                                 | Picture|
|:-----------------------------------------------------------------------------------------------------:|:-----:|
|**``FormConverter``**:<br>Text = "BGN to EUR",<br>Font.Size = 12,<br>MaximizeBox = False,<br>MinimizeBox = False,<br>FormBorderStyle = FixedSingle | [image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/13.Currency-converter-04.png 
        alt="Form Converter" /]  |
|**``numericUpDownAmount``**:<br>Value = 1,<br>Minimum = 0,<br>Maximum = 10000000,<br>TextAlign = Right,<br>DecimalPlaces = 2 | [image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/13.Currency-converter-05.png  alt="Numeric Up Down" /] |
|**``labelResult``**:<br>AutoSize = False,<br>BackColor = PaleGreen,<br>TextAlign = MiddleCenter,<br>Font.Size = 14,<br>Font.Bold = True| [image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/13.Currency-converter-06.png alt="Label Result" / |
[/slide]

[slide]
#### Events and eventhandlers

We difine the following **eventhandlers** in the controls:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/13.Currency-converter-07.png 
       alt="EventHandler" /] 

After this we catch the following events:
- **``FormConverter.Load``** (by clicking on the form twice with the mouse)
- **``numericUpDownAmount.ValueChanged``** (by clicking on **``NumericUpDown``** control twice)
- **``numericUpDownAmount.KeyUp``** (we choose **``Events``** from the dashboard **``Properties``** and click twice on **``KeyUp``**)

The event **`Form.Load`** is executed when the program is started, before the window of the application is shown. The event **`NumericUpDown.ValueChanged`** is executed when a change in the value inside the field for entering a number occurs. The event **`NumericUpDown.KeyUp`** is executed after pressing a key in the field that enters a number. On the occurance of each of these events, we will recalculate the result.

To **catch an event** we use the events icon (Events) in the **Properties**  window in Visual Studio:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/13.Currency-converter-08.png 
       alt="Events in Visual Studio" /] 
[/slide]

[slide]
#### Writing the program code and testing the application

We will use the following **C# code** for handling events:

```csharp
private void FormConverter_Load(object sender, EventArgs e)
{
ConvertCurrency();
}

private void numericUpDownAmount_ValueChanged(object sender, EventArgs e)
{
ConvertCurrency();
}

private void numericUpDownAmount_KeyUp(object sender, KeyEventArgs e)
{
ConvertCurrency();
}
```

All of the caught events call out the method **`ConvertCurrency()`**, which converts the given sum from levs to euro and shows the result int the green box.

We have to wrtite the **code** (program logic) for converting from levs to euro: 

```csharp
private void ConvertCurrency()
{
var amountBGN = this.numericUpDownAmount.Value;
var amountEUR = amountBGN * 1.95583m;
this.labelResult.Text = 
    amountBGN + " BGN = " + 
    Math.Round(amountEUR, 2) + " EUR";
}
```

In the end **we start the project** with [**Ctrl+F5**] and test if it works correctly.

If you have any problems with the example above, **watch the video** in the begging of this chapter. There, the application is being built live, step by step, with a lot of explanations. Or ask a question in the [anchor href=https://softuni.bg/forum]**forum of SoftUni**[/anchor].
[/slide]

[slide]
### Graphical application: \*\*\* Catch the button!

Create a fun graphical application **„catch the button“**: a form consisting of one button. By moving the mouse cursor onto the button, it moves on random position. This way it creates the impression that **„the button runs form the mouse and it is hard to catch"**. When the button gets „caught“, a congratulations message is shown.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-images/14.Catch-the-button-01.png 
       alt="Catch the Button App" /]

**Hint**: write an eventhandler **``Button.MouseEnter``** and move the button on random position. Use the generator for random numbers **``Random``**. The position of the button is set from the property **``Location``**. To make sure the new position of the button is in the form's borders, you can make calculations based on the size of the form, which is available from the **``ClientSize``** property. You may use the following sample code:

```csharp
private void buttonCatchMe_MouseEnter(object sender, EventArgs e)
{
    Random rand = new Random();
    var maxWidth = this.ClientSize.Width - buttonCatchMe.ClientSize.Width;
    var maxHeight = this.ClientSize.Height - buttonCatchMe.ClientSize.Height;
    this.buttonCatchMe.Location = new Point(
        rand.Next(maxWidth), rand.Next(maxHeight));
}
```
[/slide]