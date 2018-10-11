[slide]
# Intro to Programming - Exercises
[img src="img/intro-progrmming-exercises.png" align="center"]
## Learn How to Write Simple Programs in C#

[video src="https://youtu.be/gfs2fs2"]


[slide]
# Exercise: Rectangle Area

Write a program that enters two sides of a rectangle, numbers `a` and `b`, and calculates and prints the **rectangle area** `s` = `a` * `b`.

## Sample Input / Output

[input-output-table]
	[input]2
	7[/input]
	[output]14[/output]
	[comments]`s` = `a` * `b` = `2` * `7` = `14`[/comments]

	[input]9
	6[/input]
	[output]54[/output]
	[comments]`s` = `a` * `b` = `9` * `6` = `54`[/comments]

	[input]10
	10[/input]
	[output]100[/output]
[/input-output-table]

Write your code below:

```csharp [must-solve]
[fixed]
using System;

class Rectangle
{
	static void Main()
	{
[/fixed]
		// TODO: write your code here ...
		[hint]
		var a = double.Parse(Console.ReadLine());
		[/hint]
		[hint]
		var b = double.Parse(Console.ReadLine());
		[/hint]
		[hint]
		var s = // TODO: multiply a * b
		Console.WriteLine(s);
		[/hint]
[fixed]
	}
}
[/fixed]

[input]2
7[/input]
[output]14[/output]

[input]12
5[/input]
[output]60[/output]

[input]3
0[/input]
[output]0[/output]

[checker integer-number-compare skip-all-text]
```
