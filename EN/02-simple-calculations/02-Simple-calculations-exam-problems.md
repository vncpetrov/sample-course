[slide]
# Chapter 2.2. Simple Calculations - Exam Problems

In the previous chapter, we explained how to work with the system console - how to **read numbers** from it and how to **print the output**. We went through the main arithmetical operations and briefly mentioned data types. Now, we are going to practice what we have learned by solving a few **more complex exam problems**. 
[/slide]

[slide]
## Reading Numbers from the Console

Before going to the tasks, we are going to revise the most important aspects of what we have studied in the previous chapter. We will start with reading numbers from the console.

### Reading an integer

We need to create a variable to store the integer (for example, **`num`**) and use a standard command for reading input from the console, combined with the function **`int.Parse(…)`** which converts string to an integer:

```csharp
var num = int.Parse(Console.ReadLine());
```

### Reading a decimal number

We read a decimal number, the same way we read an integer one, but this time we use the function **`double.Parse(…)`**:

```csharp
var num = double.Parse(Console.ReadLine());
```
[/slide]

[slide]
## Using placeholders

**Placeholder** is an expression which is replaced with a particular value while printing an output. The methods **`Console.Write(…)`** / **`WriteLine(…)`** support printing a string pattern, where the first argument is the formatted string, followed by the number of arguments, equal to the number of placeholders.

```csharp
Console.WriteLine("You are {0} {1}, a {2}-years old person from {3}.",
  firstName, lastName, age, town);
```
[/slide]

[slide]
## Arithmetical operators

Let' s revise the main arithmetical operators for simple calculations.

### Operator +

```csharp
var result = 3 + 5; // the result is 8
```

### Operator -

```csharp
var result = 3 - 5; // the result is -2
```

### Operator *

```csharp
var result = 3 * 5; // the result is 15
```

### Operator /

```csharp
var result = 7 / 3; // the result is 2 (integer division)
var result2 = 5 / 2.0; // the result is 2.5 (floating-point division)
```
[/slide]

[slide]
## Concatenation

By using the operator **`+`** between string variables (or between a string and a number), concatenation is being made (combining strings).

```csharp
var firstName = "Ivan";
var lastName = "Ivanov";
var age = 19;
var str = firstName + " " + lastName + " is " + age + " years old";
// Ivan Ivanov is 19 years old
```
[/slide]

[slide]
## Exam Problems

Now, after having revised how to make simple calculations and how to read and print numbers from the console, let' s go to the tasks. We will solve a few **problems from a SoftUni entrance exam**.

## Problem: Training Lab

**A training lab** has a rectangular size **l** to **w** meters, without columns on the inside. The hall is divided in two parts- left and right, with a hallway approximately in the middle. In both of the parts, there are **rows with desks**. In the back of the hall, there is a big **entrance door** and in the front, there is a **podium** for the lecturer. A single **working place** takes up **70 to 120 cm** (a table with size 70 to 40 cm + space for a chair with size 70 to 80 cm). **The hallway** width is at least **100 cm**. It is calculated that due to the **entrance door** (which is with 160 cm opening), **exactly one working space is lost**, and due to the **podium** (which is with size 160 to 120 cm), exactly **two working spaces** are lost. Write a program that receives the size of the training lab as input parameters and calculates the **number of working places in it **(look at the figure).

### Input Data

**Two numbers** are read from the console, one per line: **l** (length in meters) and **w** (width in meters).

Constraints: **3 ≤ w ≤ l ≤ 100.**

### Output Data

Print an integer: the **number of working places** in the training lab.

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]
[/slide]

[slide]
### Sample Input and Output

| Input   | Output | Figure |
|---------|-------|--------|
|15<br>8.9  |129  | [image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/01.Training-lab-01.png alt="Training Lab" /] |
|8.4<br>5.2 |39   | [image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/01.Training-lab-02.png alt="Training Lab" /] |

#### Clarification of the examples:

In the first example, the hall length is 1500 cm. **12 rows** can be situated in it (12 * 120 cm = 1440 + 60 cm difference). The hall width is 890 cm. 100 cm from them are for the hallway in the middle. The rest 790 cm can be situated by **11 desks per row** (11 * 70 cm = 770 cm + 20 cm difference). **Number of places = 12 * 11 - 3** = 132 - 3 = **129** (we have 12 rows with 11 working places = 132 minus 3 places for podium and entrance door).

In the second example, the hall length is 840 cm. **7 rows** can be situated in it (7 * 120 cm = 840, no difference). The hall width is 520 cm. 100 cm from them are for the hallway in the middle. The rest 420 cm can be situated by **6 desks per row** (6 * 70 cm = 420 cm, no difference). **Number of places = 7 * 6 - 3** = 42 - 3 = **39** (we have 7 rows with 6 working places = 42 minus 3 places for podium and entrance door).
[/slide]

[slide]
### Hints and Guidelines

Try to solve the problem on your own first. If you do not succeed, go through the hints.

#### Idea for Solution

As it is with any programming task, **it is important to build an idea for its solution**, before having started to write code. Let' s carefully go through the problem requirements. We have to write a program that calculates the number of working places in a training lab, where the number depends on the hall length and height. We notice that the received input will be **in meters** and the information about how much space the working places and hallway take, will be **in centimeters**. To do the calculations, we will use the same measuring units, no matter whether we choose to convert length and height to centimeters or the other data in metres. The first option is used for the presented solution.  

Next, we have to calculate **how many columns and how many rows** with desks will fit. We can calculate the columns by **subtracting the width by the necessary space for the hallway (100 cm) and divide the difference by 70 cm** (the length of a working place). We find the rows by **dividing the length by 120 cm**. Both operations can result in **a real number** with whole and fractional part but we have to **store only the whole part in a variable**. In the end, we multiply the number of rows by the number of columns and divide it by 3 (the lost places for entrance door and podium). This is how we calculate the wanted value.
[/slide]

[slide]
#### Choosing Data Types

From the example, we see that a real number with whole and fractional part can be received as an input, therefore, it is not appropriate to choose data type **`int`**. This is why we use **`double`**. Choosing data type for the next variables depends on the method we choose to solve the problem. As with any programming task, this one has **more than one way to be solved**. Two methods will be shown here. 

#### Solution - part I

It is time to go to the solution. We can divide it into three smaller tasks: 
* **Reading input from the console**.
* **Doing the calculations**.
* **Printing the output on the console**.

The first thing we have to do is read the input from the console. With **`Console.ReadLine()`** we read the values from the console and with the function **`double.Parse(…)`** string is converted into **`double`**.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/01.Training-lab-03.png alt="Code" /]

Let' s go to the calculations. The special part here is that after having divided the numbers, we have to store only the whole part of the reslt in a variable. 

<table><tr><td><img src="https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/alert-icon.png" style="max-width:50px" /></td>
<td><b>Search in Google!</b> Whenever we have an idea how to solve a particular problem but we do not know how to write it in C# or we are dealing with one that many other people have had before us, the easiest way to solve it is by looking for information on the Internet.</td>
</tr></table>

In this case, we can try with the following search: [anchor href=https://www.google.com/?q=c%23+get+whole+number+part+of+double]**c# get whole number part of double**[/anchor]. One possible way is to use the method **`Math.Truncate(…)`** as it works with **`double`** data types. For the number of rows and columns we create variables of the same type.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/01.Training-lab-04.png alt="Code" /]
[/slide]

[slide]
#### Solution - part II

Second method: As we already know, the operator for division **`/`** operates differently on integers and decimals. **When dividing integer with integer, the result is also an integer**. Therefore, we can search how to convert the real numbers, which we have as values for the heigth and the width, into integers and then divide them. 

In this case, there could be **data loss** after having removed the fractional part, so it is necessary that it is converted **expressly** (explicit typecasting). We use the operator for converting data **`(type)`** by replacing the word **type** with the needed **data type** and place it **before the variable**. (you can learn more about data type conversion here [anchor href=http://www.introprogramming.info/intro-csharp-book/read-online/glava3-operatori-i-izrazi/#_Toc298863977]Svetlin Nakov, Veselin Kolev and team: "Programming Basics with C#", стр. 153-157[/anchor]). 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/01.Training-lab-05.png alt="Code" /]

With **`Console.WriteLine(…)`** we print the result on the console.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/01.Training-lab-06.png alt="Code" /]

### Test in the Judge system

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/505#0]           
                            https://judge.softuni.bg/Contests/Practice/Index/505#0
                         [/anchor].

[/slide]

[slide]
## Problem: Vegetable Market

A gardener is selling his harvest on the vegetable market. He is selling **vegetables for N levs per kilogram** and **fruits for M levs per kilogram**. Write a program that **calculates the earnings of the harvest in euro** (if **one euro** equals **1.94 lv.**).

### Input Data

**Four numbers** are read from the console, one per line: 

* First line - Price per kilogram for vegetables - a floating-point number.
* Second line - Price per kilogram for fruits - a floating-point number.
* Third line - Total kilograms of vegetables - an integer.
* Fourth line - Total kilograms of fruits - an integer. 

**Constraints: All numbers will be in the interval between 0.00 and 1000.00**

### Output Data

Print on the console **one floating-point number: the earnings of all fruits and vegetables in euro**.

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]

### Sample Input and Output

| Input   | Output  |
|-----------|----------|
|0.194<br>19.4<br>10<br>10|101 | 

**Clarification for the first example:**

* Vegetables cost: 0.194 lv. \* 10 kg. = **1.94 lv.**
* Fruits cost: 19.4 lv. \* 10 kg.  = **194 lv.**
* Total: **195.94 lv. = 101 euro**. 

| Input    | Output      |
|-----------|----------------|
|1.5<br>2.5<br>10<br>10|20.6185567010309| 
[/slide]

[slide]
### Hints and Guidelines

First, we will give a few ideas and particular hints for solving the problem, followed by the essential part of the code.  

#### Idea for Solution

Let' s first go through the problem requirements. In this case, we have to calculate the **total income** from the harvest. It equals **the sum of the earnings from the fruits and the vegetables** which we can calculate by multiplying **the price per kilogram by the quantity**. The input is received in lev and the output should be in euro. It is accepted that 1 euro equals 1.94 lev, therefore, in order to get the wanted **output value, we have to divide the sum by 1.94**.
[/slide]

[slide]
#### Choosing Data Types

After we have a clear idea on how to solve the task, we can continue with choosing appropriate data types. Let' s go through the **input**: we have **two integers** for total kilograms of vegetables and fruits, therefore, the variables we declare to store their values will be of type **`int`**. The prices of the fruits and vegetables are said to be floating-point numbers, therefore, the variables will be of type **`double`**.

We can also declare two variables to store the income from the fruits and vegetables separately. As we are multiplying a variable of type **`int`** (total kilograms) with one of type **`double`** (price), the result should also be of type **`double`**. Let' s clarify that: generally, **operators work with arguments of the same type**. Therefore, in order to multiply values from different data types, we have to convert them to the same type. When there are types of different scopes in one expression, the one with the highest scope is the one the other types are converted to, in this case, **`double`**. As there isn' t danger of data loss, **the conversion is implicit** and is automatically done by the compiler. 

The **output** should also be a **floating-point number**, therefore, the result will be stored in a variable of type **`double`**.
[/slide]

[slide]
#### Solution 

It is time to get to the solution. We can divide it into three smaller tasks:  
* **Reading input from the console**.
* **Doing the calculations**.
* **Printing the output on the console**.

In order to read the input, we declare variables, which we have to name carefully, so that they can give us a hint about the values they store. With **`Console.ReadLine(…)`**, we read values from the console and with the the functions **`int.Parse(…)`** and **`double.Parse(…)`**, we convert the particular string value into **`int`** and **`double`**.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/02.Vegetable-market-01.png alt="Code" /]

We do the necessary calculations:  

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/02.Vegetable-market-02.png alt="Code" /]

The task does not specify special output format, therefore, we just have to calculate the wanted value and print it on the console. As in mathematics and so in programming, division has a priority over addition. However, in this task, first we have to **calculate the sum** of the two received values and then **divide by 1.94**. In order to give priority to addition, we can use brackets. With **`Console.WriteLine(…)`** we print the output on the console. 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/02.Vegetable-market-03.png alt="Code" /]

### Test in the Judge system

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/505#1]           
                            https://judge.softuni.bg/Contests/Practice/Index/505#1
                         [/anchor].
[/slide]

[slide]
## Problem: Change Tiles

**The tiles** on the ground in front of an apartment building **need changing**. The ground has a **square shape with side N metres**. The tiles are **wide "W" metres** and **long "L" metres**. There is one bench on the ground with **width M metres and length O metres**. The tiles under it are not necessary to be replaced. Each tile is replaced for **0.2 minutes**.

Write a program that **reads the size of the ground, the tiles and the bench from the console**, and calculates how many tiles are necessary to cover the ground and **the total time for replacing the tiles**. 

**Example: ground with size 20 m.** has **аrea 400 sq.m.**. **A bench** that is **1 m.** wide and **2 m.** long, has area of **2 sq.m.**. **One tile** is **5 m. wide, 4 m. long** and has **area of 20 sq.m.**. The space that needs to be covered is **400 – 2 = 398 sq.m.**. **398 / 20 = 19.90 tiles** are necessary. The **time** needed is **19.90 * 0.2 = 3.98 minutes.******

### Input Data

**5 numbers** are read from the console: 

* **N – length** of **a size** from **the ground** in the range of [**1 … 100**].
* **W – width** per **tile** in the range of [**0.1 … 10.00**].
* **L – length** per **tile** in the range of [**0.1 … 10.00**].
* **М – width** of **the bench** in the range of [**0 … 10**].
* **О – length** of **the bench** in the range of [**0 … 10**].

### Output Data

Print on the console **two numbers**: **number of necessary tiles** for the repair and the **total time for changing them**, each on a new line.

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]		

### Sample Input and Output

| Input        | Output    |
|---------------|------------|
|20<br>5<br>4<br>1<br>2|19.9<br>3.98| 

**Explanation of the example:**

* **Total area** = 20 \* 20 = 400.
* **Area of the bench** = 1 \* 2 = 2.
* **Area for covering** = 400 – 2 = 398.
* **Area of tiles** = 5 \* 4 = 20.
* **Necessary tiles** = 398 \/ 20 = 19.9.
* **Necessary time** = 19.9 \* 0.2 = 3.98.

| Input    | Output            |
|-----------|--------------------|
|40<br>0.8<br>0.6<br>3<br>5|3302.08333333333<br>660.416666666667| 
[/slide]

[slide]
### Hints and Guidelines

Let's make a draft to clear the task requirements. It can look the following way: 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/03.Change-tiles-01.png alt="Draft" /]

#### Idea for Solution

It is required to calculate **the number of tiles** that have to be changed, as well as **the total time for replacing them**. In order to find the **number of tiles**, we have to calculate the **area that needs to be covered** and **divide it by the area per tile**.The ground is square, therefore, we find the total area by multiplying its side by its value **`N * N`**. After that, we calculate **the area that the bench takes up** by multiplying its two sides as well **`M * O`**. After subtracting the area of the bench by the area of the whole ground, we receive the area that needs to be repaired.

We calculcate the area of a single tile by **multiplying its two sides with one another** **`W * L`**. As we already stated, now we have to **divide the area for covering by the area of a single tile**. This way, we find the number of necessary tiles which we multiply by **0.2** (the time needed for changing a tile). Now, we have the wanted output.
[/slide]

[slide]
#### Choosing Data Types

The length of the side of the ground, the width and the length of the bench, will be given as **integers**, therefore, in order to store their values, we can declare **variables of type `int`**. We will be given floating-point numbers for the width and the length of the tiles and this is why we will use **`double`**. The output will be a floating-point number as well, so the variables will be of type **`double`** as well.

#### Reading the Input Data

As in the previous tasks, we can divide the solution into three smaller tasks:
* **Reading the input from the console**.
* **Doing the calculations**.
* **Printing the output** on the console.

The first thing we have to do, is go through **the input** of the task. It is important to pay attention the the sequence they are given in. With **`Console.ReadLine(…)`** we read values from the console and with **`int.Parse(…)`** and **`double.Parse(…)`**, we convert the particular string value into **`int`** or **`double`**.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/03.Change-tiles-02.png alt="Code" /]
[/slide]

[slide]
#### Doing the Calculations

After we have initialized the variables and have stored the corresponding values in them, we go to the **calculations**.As the values of the variables **`n`**, **`a`** and **`b`** are stored in variables of type **`int`**, we can also declare **variables of the same type** for the results. 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/03.Change-tiles-03.png alt="Code" /]

The variables **`w`** and  **`h`** are of type **`double`**, therefore, for **the area of a single tile**, we create a variable of the same type. Finally, **we calculate the values that we have to print** on the console. **The number** of necessary **tiles** is received by **dividing the area that needs to be covered by the area of a tile**. When dividing the two numbers, one of which is **a floating-poing number**, the result will also be **a floating-point number**. Therefore, in order for the calculations to be correct, we store the result in a variable of type **`double`**. The task does not specify special formatting or rounding of the output, so we just print the values with **`Console.WriteLine(…)`**. 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/03.Change-tiles-04.png alt="Code" /]

### Testing in the Judge System

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/505#2]           
                            https://judge.softuni.bg/Contests/Practice/Index/505#2
                         [/anchor].
[/slide]

[slide]
## Problem: Money

Some time ago, **Pesho bought himself bitcoins**. Now, he is going on a tour in Europe and **he needs euro**. Apart from bitcoins, he has **Chinese yuan** as well. Pesho wants to **exchange his money in euro** for the tour. Write a program that calculates **how much euro he can buy, depending on the following exchange rates**:  
* **1 bitcoin = 1168 levs.**
* **1 Chinese yuan = 0.15 dollars.**
* **1 dollar = 1.76 levs.**
* **1 euro = 1.95 levs.**

The exchange office has **commission from 0 to 5 percent from the final sum in euro**. 

### Input Data

Three numbers are read from the console: 
* On the first line – **number of bitcoins**. Integer in the range of [**0 … 20**].
* On the second line – **number of Chinese yuan**. Floating-point number of [**0.00 … 50 000.00**].
* On the third line – **commission**. Floating-point number of [**0.00 … 5.00**].
* 
### Output Data

Print one number on the console - **the result of the exchange of the currencies**. Rounding is not necessary. 

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]

### Sample Input and Output

| Input        | Output    |
|---------------|------------|
|1<br>5<br>5|569.668717948718| 

**Explanation**: 
* 1 bitcoin = 1168 levs
* 5 Chinese yuan = 0.75 dollars 
* 0.75 dollars = 1.32 levs 
* **1168 + 1.32 = 1169.32 levs = 599.651282051282 euro**
* **Commission:** 5% от 599.651282051282 = **29.9825641025641** 
* **Result**: 599.651282051282 - 29.9825641025641 = **569.668717948718 euro**

| Input        | Output            | Input         | Output            |
|------------|------------------|--------------|------------------|
|20<br>5678<br>2.4|12442.2442010256|7<br>50200.12<br>3|10659.4701177436|
[/slide]

[slide]
### Hints and Guidelines

Let's first think of the way we can solve the task again, before having started to write code.

#### Idea for Solution

We see that the **number of bitcoins** and the **number of Chinese yuans** will be given in the input. The **output** should be in **euro**. The exchange rates that we have to work with, are specified in the task. We notice that we can only exchange the sum in lev to euro, therefore, we **first have to calculate the whole sum that Pesho has in lev**, and **then calculate the output**.

As we have information for the exhange rate of bitcoins to levs, we can directly exchange them. On the other hand, in order to get the value of **Chinese yuans in levs**, first we have to **exchange them in dollars**, and then **the dollars to levs**. Finally, we will **sum the two values** and calculate how much euro that is. 

Only the final step is left: **calculating the commission** and subtracting the new sum from the total one. We will receive **an integer** for the commission, which will be a particular **percent from the total sum**. Let' s divide it by 100, so as to calculate its **percentage value** and then multiply it by the sum in euro. We will divide the result from the same sum and print the final sum on the console. 

#### Choosing Data Types

**Bitcoins** are given as **an integer**, therefore, we can declare a **variable of type `int`** for their value. For **Chinese yuan and commission** we receive **a floating-point number**, therefore, we are going to use **`double`**. As **`double`** is the data type with bigger scope, and the **output** should also be **a floating-point number**, we will use it for the other variables we create as well.
[/slide]

[slide]
#### Solution - part I

After we have build an idea on how to solve the task and we have chosen the data structures that we are going to use, it is time to get to **writing the code**. As in the previous tasks, we can divide the solution into three smaller tasks:
* **Reading input from the console**.
* **Doing the calculations**.
* **Printing the output** on the console.

**We declare the variables** that we are going to use and again we have to choose **meaningful names**, which are going to give us hints about the values they stpre. We initialize their values: with **`Console.ReadLine(…)`**, we read the input numbers from the console and convert the entered by the user string to **`int`** or **`double`**. 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/04.Money-01.png alt="Code" /]

We do the necessary calculations: 

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/04.Money-02.png alt="Code" /]

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/04.Money-03.png alt="Code" /]

Finally, we **calculate the commission value** and **subtract it from the sum in euro**. Let' s pay attention to the way we could write this: **`euro -= commission * euro`** is the short way to write **`euro = euro - (commission * euro)`**. In this case, we use **a combined assignment operator** (**`-=`**) that **subtracts the value of the operand to the right from the one to the left**. The operator for multiplication (**`*`**) has a **higher priority** than the combined operator, this is why, the expression **`commission * euro`** is performed first and then its value is divided. (you can read more about operators here [anchor href=http://www.introprogramming.info/intro-csharp-book/read-online/glava3-operatori-i-izrazi/#_Toc298863965]Svetlin Nakov, Veselin Kolev and team: "Programming Basics with C#", page. 150[/anchor])
[/slide]

[slide]
#### Solution - part II

The task does not specify special string formatting or rounding the result, therefore, we just have to calculate the output and print it on the console.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/04.Money-04.png alt="Code" /]

Let' s pay attention to something that applies to all other problems of this type: written like that, the solution of the task is pretty detailed. As the task itself is not too complex, in theory, we could write one big expression, where right after having received the input, we calculate the output. For example, such expression would look like this:

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/04.Money-05.png alt="Code" /]

This code would print a correct result, but it is **hard to read**. It won't be easy to find out how it works and whether it contains any mistakes, as well as finding one and correcting it. **Instead of one complex expression, it is better to write a few simpler ones** and store their values in variables with appropriate names. This way, the code is more clean and easily maintainable.  

### Test in the Judge system

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/505#3]           
                            https://judge.softuni.bg/Contests/Practice/Index/505#3
                         [/anchor]
[/slide]

[slide]
## Problem: Daily Earnings

Ivan is a programmer in an **American company** and he **works** at home **approximately N days per month** by earning **approximately M dollars per day**. At the end of the year, Ivan **receives a bonus**, which **equals 2.5 of his monthly salaries. 25% of his annual salary goes for taxes**. Write a program that calculates **how much are Ivan' s net average earnings in lev per day**, as he spends them in Bulgaria. It is accepted that **one year has exactly 365 days. The exchange rate of dollar** to lev will be **read from the console**. 

### Input Data

**Three numbers** are read from the console.
* On the first line – **work days per month**. An integer in the range of [**5 … 30**].
* On the second line – **daily earnings**. A floating-point number in the range of [**10.00 … 2000.00**].
* On the third line – **exchange rate of dollar to lev** /1 dollar = X lev/. A floating-point number in the range of [**0.99 … 1.99**].

### Output Data

Print **one number** on the console - **the daily earnings in lev**. The result will be **rounded to the second decimal point**. 

[task]  
    [code-editor language=csharp]
    [/code-editor]
[/task]	

### Examples

| Input        | Output          |
|---------------|------------------|
|21<br>75.00<br>1.59|74.61| 

**Explanation**:
* **One monthly salary** = 21 \* 75 = 1575 dollars.
* **Annual income** = 1575 \* 12 + 1575 \* 2.5 = 22837.5 dollars.
* **Taxes** = 25% of 22837.5 = 5709.375 levs.
* **Net annual income** = 17128.125 dollars = 27233.71875 levs.
* **Average earnings per day** = 27233.71875 / 365 = 74.61 levs.

| Input        | Output            | Input         | Output    |
|-------------|------------------|-------------|------------------|
|15<br>105<br>1.71|80.24|22<br>199.99<br>1.50|196.63|
[/slide]

[slide]
### Hints and Guidelines

Firstly, we have to analyze the task and think of a way to solve it. Then, we will choose data types and, finally, we will write the code.

#### Idea for Solution

Let' s first calculate **how much the monthly salary** of Ivan is. We do that by **multiplying the working days per month by his daily earnings**. Firstly, we multiply the number by 12, so as to calculate his salary for 12 months, and then, we multiply it **by 2.5 ** in order to calculate the bonus. After having summed the two values, we calculate his **annual income**. Then, we **divide 25% of it**. We can do that by multiplying the total income by **0.25** and divide the result by it. Depending on the exchange rate, we **exchange the dollars to levs** and after that we **divide the result by 365 (days per year)**.  

#### Choosing Data Types

**The working days** per month are given as **an integer**, therefore, we can declare a variable of **type `int`** to store their value. For both **the earned money** and **the exchange rate of dollar to lev**, we will receive **a floating-point number**, therefore, we will use **`double`**. As **`double`** is the data type with **the higher scope**, and the output should also be **a floating-point number**, we use **`double`** for the other variables that we create as well. 
[/slide]

[slide]
#### Reading the Input Data and Doing the Calculations

Again: after we have an idea on how to solve the problem and we have considered the data types that we are going to use, we can start **writing the program**. As in the previous tasks, we can divide the solution into three smaller tasks: 
* **Reading the input from the console**.
* **Doing the calculations**.
* **Printing the output** on the console.

**We declare the variables** that we are going to use by trying to choose **meaningful names**. With **`Console.ReadLine(…)`** we read the input numbers from the console and we **convert** the input string to **`int`** or **`double`** with **`int/double.Parse(…)`**.

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/05.Daily-earnings-01.png alt="Code" /]

We do the calculations:  

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/05.Daily-earnings-02.png alt="Code" /]

We could write an expression that calculates the annual income without brackets as well. As multiplication is an operation that has a higher priority over addition, it will be performed first. Despite that, **writing brackets is recommended** when using more operators, as this way, the code is **easily readable** and chances of making a mistake are smaller. 
[/slide]

[slide]
#### Printing the Result

Finally, we have to print the result on the console. We notice that **the number has to be rounded to the second decimal point**. In order to do that, we can use a **placeholder - a place that will be replaced by a paricular value when printing**. In C#, a digit surrоunded by curly brackets, is used for a **placeholder**. As **in programming counting starts from 0**, the expression **`{0}`** means that it will be replaced by the first given argument. An integer or a floating-point number we can format by using **F** or **f**. That is followed by a whole positive number, which specifies the number of digits after the point (you can read more about formatting here: [anchor href=http://www.introprogramming.info/intro-csharp-book/read-online/glava4-vhod-i-izhod-ot-konzolata/#_Toc298863992]Svetlin Nakov, Veselin Kolev and team: "Programming Basics with C#", page. 155-158[/anchor]):  

[image src=https://github.com/SoftUni/Programming-Basics-Book-CSharp-EN/blob/master/assets/chapter-2-2-images/05.Daily-earnings-03.png alt="Code" /]

### Test in the Judge system

Test your solution here: [anchor href=https://judge.softuni.bg/Contests/Practice/Index/505#4]           
                            https://judge.softuni.bg/Contests/Practice/Index/505#4
                         [/anchor].
[/slide]