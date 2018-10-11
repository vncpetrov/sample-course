[slide]
# What is Programming?
[img src="img/what-is-programming.png" align="center"]
## Programming, Commands, Code, Programs

[video src="https://youtu.be/gfs2fs2"]


[slide]
# What Does "Programming" Mean?
 - We give commends to the computer, to "communicate"
   - We write the commands, one after another
   - In a sequence, the commands construct a "computer program"
 - Programs are written in **programming languages**
   - E.g. C#, Java, JavaScript, Python, PHP, C, C++
   - In an integrated development environment (IDE), like IntelliJ IDEA or Visual Studio

[details]
Programming means to "write computer programs", i.e. to write a sequence of instructions (commands) that the computer should execute, one after another. 

...

We use programming languages, like C# and Java, to write our code...


[slide]
# Computer Programs
 - **Program** == sequence of commands
   - Can hold commands, calculations, condition checks, reprtitions, ...
 - Programs are written in text format
   - The program's text is called "**source code**"
 - ...

[details]
...


[slide]
# Computer Programs - Examples

A program that prints "*Hello*":

```csharp [must-run]
[hidden]
using System;

class Example
{
	static void Main()
	{
[/hidden]
		Console.WriteLine("Hello");
[hidden]
	}
}
[/hidden]
```

[slide]
# Exercise: Modify the Code

Now, modify the program below to print "*Nice*":

```csharp
[hidden]
using System;

class Example
{
	static void Main()
	{
[/hidden]
		Console.WriteLine("Hello");
[hidden]
	}
}
[/hidden]
[input][/input]
[output]Nice[/output]
```


[slide]
# Convert BGN to EUR - Example

Play with the program below. Calculate how many EURs are:
 - 5 leva
 - 1200 leva
 - 0 leva

```csharp
[must-run count=3]
[hidden]
using System;

class Example
{
	static void Main()
	{
[/hidden]
		var leva = int.Parse(Console.ReadLine());
		var euro = leva / 1.95583;
		Console.WriteLine(euro);
[hidden]
	}
}
[/hidden]

[input]5[/input] [output]2.55646[/output]
[input]1200[/input] [output]613.55026[/output]
[input]0[/input] [output]0[/output]
[checker number-compare precision="0.0001"]
```
