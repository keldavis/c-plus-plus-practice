# Introduction to C++
## A simple repository that teaches the basics of C++

This project is my coding journal. I am learning C++ from scratch and sharing my lessons with you. Hopefully, this will be a great tutorial. 

## Table of Contents
- [Hello World](#Hello-World)
- [Comments](#Comments)
- [#Include](#include)
- [The main function](#The-main-function)
- [Curly braces](#Curly-braces)
- [standard library](#Using-the-standard-library-for-output)
- [The return statement](#The-return-statement)
- [Compile and Execute](#Compile-and-Execute)
- [Variables](#variables)
- [Basic Data Types](#Basic-Data-Types)
- [Basic Programs](#Basic-Programs)

### Hello World

The "Hello World!" program is a basic and small program. 

```
// a small C++ program
#include <iostream>
int main(){
	std::cout << "Hello, world" << std::endl;
	return 0;
}
```

This program is useful because it's so simple that if you have trouble, the most likely reasons are typos or misunderstanding the implementation. Thoroughly understanding even such a small program can teach a surprising amount about the fundamentals of C++. In order to gain this understanding, we'll look in detail at each line of the program. 

### Comments

The first line of our program is 

```
		// a small C++ program
```

The // characters begin a comment, which extends to the end of the line. The compiler ignores comments; their purpose is to explain the program to a human reader

### #include

In C++, many fundamental facilities, such as input-output, are part of the standars library, rather than being part of the core language. This distinction is important because the core language is always available to all C++ programs, but you must explicitly ask for the parts of the standard library that you wish to use. 

Programs ask for standard-library facilities by using #include directives. Such directives normally appear at the beginning of a program. The only part of the standard library that our program uses is input-output, which we request by writing

```
	#include <iostream>
```

The name **iostream** suggests support for sequential, or stream, input-output, rather than random-access or graphical input-output. Because the name iostream appears in an #include directive and it is enclosed in **angle brackets** (< and >), it refers to a part of the C++ library called a **standard header**.

The C++ standard does not tell us exactly what a standard header is, but it does define each header's name and behavior. Including a standard header makes the associated library facilities available to the program.

### The main function

A **function** is a piece of program that has a name, and that another part of the program can **call**, or cause to run. Every C++ program must contain a function named *main*. When we ask the C++ implementation to run a program, it does so by calling this function.

The *main* function is required to yield an integer as its result, the purpose of which is to tell the implementation whether the program ran successfully. A zero value indicates success; any other value means there was a problem. Accordingly, we begin by writing

```
	int main()
```

to say that we are defining a function named *main* that returns a value of type int. Here, *int* is the name that the core language uses to describe integers. The parentheses after *main* enclose the parameters that our function receives from the implementation. In this particular example, there are no parameters, so there is nothing between the parentheses.

### Curly braces

We continue our definition of the main function by following the parentheses with a sequence of statements enclosed in curly braces (often simply called braces):


```
	int main() 
	{                // left brace                 
					// the statements go here 
	}                // right brace
```

In C++, braces tell the implementation to treat whatever appears between them as a unit. In this example, the left brace marks the beginning of the statements in our main function, and the right brace marks their end. In other words, the braces indicate that all the statements between them are part of the same function.

When there are two or more statements within braces, as there are in this function, the implementation executes them in the order in which they appear.

### Using the standard library for output

The first statement inside the braces does our program's real work:

```
	std::cout << "Hello, world!" << std::endl;
```

This statement uses the standard library's **output operator**, *<<*, to write *Hello, world!* on the standard output, and then to write the value of *std::endl*. 

Preceding a name by *std::* indicates that the name is part of a **namespace** named std. A namespace is a collection of related names; the standard library uses std to contain all the names that it defines. So, for example, the *iostream* standard header defines the names *cout* and *endl*, and we refer to these names as *std::cout* and *std::endl*. 

The name *std::cout* refers to the **standard output stream**, which is whatever facility the C++ implementation uses for ordinary output from programs. In a typical C++ implementation under a windowing operating system, *std::cout* will denote the window that the implementation associates with the program while it is running. Under such a system, the output written to *std::cout* will appear in the associated window. 

Writing the value of *std::endl* ends the current line of output, so that if this program were to produce any more output, that output would appear on a new line.

### The return statement

A return statement, such as 

```
	return 0;
```

ends execution of the function in which it appears, and passes the value that appears between the *return* and the semicolon (*0* in this example) back to the program that called the function that is returning. The value that is returned must have a type that is appropriate for the type that the function says it will return. In the case of *main*, the return type is *int* and the program to which *main* returns is the C++ implementation itself. Therefore, a *return* from *main* must include an integer-valued expression, which is passed back to the implementation.

Of course, there may be more than one point at which it might make sense to terminate a program; such a program may have more than one return statement. If the definition of a function promises that the function returns a value of a particular type, then every return statement in the function must return a value of an appropriate type

# Compile and Execute

Compile: A computer can only understand machine code. A compiler can translate the C++ programs that we write into machine code. To compile a file, you need to type ```g++``` followed by the file name in the terminal:

``` g++ hello.cpp ```

The compiler will then translate the C++ program **hello.cpp** and create a machine code file called **a.out**.

**Execute**: To execute the new machine code file, all you need to do is type ```./``` and the machine code file name in the terminal:

```./a.out```

The executable file will then be loaded to computer memory and the computer’s CPU (Central Processing Unit) executes the program one instruction at a time.

#### Compile and Execute (Naming Executables)

**Compile**: Sometimes when we compile, we want to give the output executable file a specific name. To do so, the compile command is slightly different. We still need to write ```g++``` and the file name in the terminal. After that, there should be ```-o``` and then the name that you want to give to the executable file:

```g++ hello.cpp -o hello```

The compiler will then translate the C++ program **hello.cpp** and create a machine code file called **hello**.

**Execute**: To execute the new machine code file, all you need to do is type ```./``` and the machine code file name in the terminal: 

```./hello```

The executable file will then be loaded to computer memory and the computer’s CPU will execute the program one instruction at a time.

### The Process

C++ is a compiled language. That means that to get a program to run, you must first translate it from the human-readable form to something a machine can “understand.” That translation is done by a program called a *compiler*.

What you read and write is called *source code* (usually it’s in an English-like language like C++), and what the computer executes is called *executable, object code*, or *machine code* (a machine language).

Typically C++ source code files are given the suffix:

- **.cpp** (ex: **hello.cpp**) or
- **.h** (ex: **std_lib_facilities.h**).

#### Compile:

```g++ hello.cpp -o hello```

A compiler translates the C++ program into machine language code which it stores on the disk as a file with the extension **.o** (e.g. **hello.o**). A linker then links the object code with standard library routines that the program may use and creates an executable image which is also saved on disk, usually as a file with the file name without any extension (e.g. **hello**).

#### Execute:

```./hello```

The executable is loaded from the disk to memory and the computer’s CPU (**C**entral **P**rocessing **U**nit) executes the program one instruction at a time.

#### Running Hello World Locally:

On the Mac, it’s called the Terminal. On Windows, it’s called the Command Prompt.

Video Tutorials:

[Running Hello World via Terminal (Mac)](https://www.youtube.com/watch?v=N4796qsD-H8&feature=youtu.be)

[Running Hello World via Command Prompt (Windows)](https://youtu.be/GxHLErBLgI8)

[Using Microsoft Visual Studio Code](https://youtu.be/hKCYP4HWisE)

# Variables

- [Decare a variable](#Step-1-Declare-a-variable)
- [Initialize a Variable](#Step-2-Initialize-a-Variable)
- [Declaring and Initializing Variable](#Combining-Step-1-and-Step-2)
- [Arithmetic Operators](#Arithmetic-Operators)
- [Chaining](#Chaining)
- [User Input](#User-Input)
- [Summary of Variables Lesson](#Review)
- [Basic C++ Programs](#Basic-C++-Programs)

"Every variable in C++ must be declared before it can be used!"
Suppose we are building a game and we want to keep track of a player’s score that goes from 0 to 10. We need a variable!

### Step 1 Declare a variable

Before we can use a variable, we must declare, or create, it. To declare a variable, we need to provide two things:

- A type for the variable.
- A name for the variable.

So to declare an integer variable called score, we need to write:

```int score;```

The ```int``` is the type of the variable. 
The ```score``` is the name of the variable. 
The ```;``` is how we end a statement. 
In C++, variable names consist only of upper/lower case letters, digits, and/or underscores.

**Note**: C++ is known as a strongly typed language. If you try to give an integer value a decimal number, you are going to get unexpected results, warnings, or errors.

### Step 2 Initialize a Variable

After we declare a variable, we can give it a value!

Suppose that we have declared an ```int``` variable called ```score```, to set it to 0, we can simply write:

```score = 0;```

- The ```score``` is the name of the variable.
- The ```=``` indicates assignment.
- The ```0``` is the value you want to store inside the variable.

**Note**: In C++, a single equal sign ```=``` does not really mean “equal”. It means “assign”. In the code above, we are assigning the ```score``` variable a value of 0.

### Combining Step 1 and Step 2

We can both declare and assign a value to a variable in a single initialization statement.

Suppose we have these two lines:

```
// Declare a variable
int score;

// Initialize a variable
score = 0;
```

We can actually combine these two lines into a single line of code:

```int score = 0;```

This means we are declaring an integer called score and setting it equal to 0.

**Note**: We only need to declare a variable one time! And it is highly suggested to initialize a variable before using it later.

### Arithmetic Operators

Computers are incredible at doing calculations. Now that we have declared variables, let’s use them with *arithmetic operators* to calculate things!

Here are some arithmetic operators:

```+``` addition
```-``` subtraction
```*``` multiplication
```/``` division
```%``` modulo (divides and gives the remainder)

For example:

```
int score = 0;
// score is 0

score = 4 + 2;
// it is now 6

score = 4 - 2;
// it is now 2

score = 4 * 2;
// it is now 8

score = 4 / 2;
// and now 2

score = 5 % 2;
// and now 1
```

**Note**: The order of operations can be specified using parentheses. For example, the use of parentheses in ```score = 5 * (4 + 3)``` sets ```score``` equal to ```5 * 7``` rather than ```20 + 3```.

### Chaining

Now that we have outputted a variable and have also outputted things using multiple ```cout```s. Let’s take a closer look at ```cout``` again.

If we have the code below:

```
int age = 28;

std::cout << "Hello, I am ";
std::cout << age;
std::cout << " years old\n";
```

It will output:

```Hello, I am 28 years old```

Notice how we use quotes around the characters in "Hello, I am " but not in age.

- We use quotes when we want a literal string.
- We don’t use quotes when we refer to the value of something with a name (like a variable).

So now, is it possible to write the ```cout``` statements within a single line?

Yes! You can use multiple ```<<``` operators to *chain* the things you want to output.

For the same code above you can also do:

```
int age = 28;

std::cout << "Hello, I am " << age << " years old\n";
```

This is called **chaining**.

### User Input

As mentioned in the introduction, another way to assign a value to a variable is through user input. A lot of times, we want the user of the program to enter information for the program.

We have ```cout``` for output, and there is something called ```cin``` that’s used for input!

```
std::cout << "Enter your password: ";
std::cin >> password;
```

The name ```cin``` refers to the standard input stream (pronounced “see-in”, for **c**haracter **i**nput). The second operand of the ```>>``` operator (“get from”) specifies where that input goes.

Here's an example program:

```
#include <iostream>

int main() {
  
  int tip = 0;
  std::cout << "Enter tip amount: ";
  // Ask for user input. Put input in the variable named tip
  std::cin >> tip;
  std::cout << "You paid " << tip << " dollars \n";
}
```

Output: "You paid 0 dollars"

### Review

Here is a review of the variables lesson:

- A variable represents a particular piece of your computer’s memory that has been set aside for you to use to store, retrieve, and manipulate data.

- C++ basic data types include:
	- ```int```: integers
	- ```double```: floating-point numbers
	- ```char```: individual characters
	- ```string```: sequence of characters
	- ```bool```: true/false
- Single equal sign ```=``` indicates assignment, not equality in the mathematical sense.
- ```cin``` is how to receive input from the user.

Check out the [Variables Cheat Sheet](https://www.codecademy.com/learn/learn-c-plus-plus/modules/learn-cpp-variables/cheatsheet) from Codecademy.

# Basic Data Types

C++ provides a rather large number of types. However, you can write perfectly good programs using only five of those:

![alt text](https://s3.amazonaws.com/codecademy-content/courses/learn-cpp/variables/data-types.gif)

Here are some examples of declaring and initializing variables:

```
int age = 28;

double price = 8.99;

char grade = 'A';

std::string message = "Game Over";

bool late_to_work = true;
```

## Datatype Modifiers

As the name implies, datatype modifiers are used with built-in data types to modify the length of data that a particular data type can hold. Data type modifiers in C++ are:

- ```signed```
- ```unsigned```
- ```short```
- ```long```

## Const
```const``` (constant) variables cannot be changed by your program during execution.

```
const double quarter = 0.25;


// and now variable quarter can only be 0.25
```

Simply add the keyword const before the data type during declaration to make the variable not modifiable.

## Type Conversion

A type cast is basically a conversion from one type to another.

The notation ```(type) value``` means “convert ```value``` to ```type```“. So for example:

```
double weight1;
int weight2;

weight1 = 154.49;
weight2 = (int) weight1;

// weight2 is now 154
```

**Note**: Going from a ```double``` to an ```int``` simply removes the decimal. There’s no rounding involved.

# Basic Programs

- [Dog Years](#Dog-Years)
- [Quadratic Formula](#Quadratic-Formula)
- [Piggy Bank](#Piggy-Bank)

## Dog Years

Dogs have ages that don’t quite work like ours. This can be a little ruff when you want to know how old your dog would be if he/she is a human. Don’t fret — build a dog-age-converting program to translate your dog’s age into human years!

Here’s how we can convert your dog’s age into human years:
- The first two years of a dog’s life count as 21 human years.
- Each following year counts as 4 human years.

![alt text](https://s3.amazonaws.com/codecademy-content/courses/learn-cpp/variables/dog.gif)

So a one-year-old dog is 10.5 years old in human years, and a two-year-old dog is 21 years old in human years… hmm this is about to get more complicated. Before you start doing the math in your head, let a computer take care of it!

1. Declare an int variable named ```dog_age```, and set it equal to your dog’s age as a number.

Note: This version of the program is for dogs older than 2 years old.

2. Let’s declare three more ```int``` variables:

```early_years```: for your dog’s first two years
```later_years```: for your dog’s following years
```human_years```: for your dog’s total human years

3. “The first two years of a dog’s life count as 21 human years.”

Let’s give the variable ```early_years``` a value of 21.

4. “Each following year counts as 4 human years.”

Give the variable ```later_years``` a value of ```dog_age``` minus 2, and then multiply by 4.

5. Add ```early_years``` and ```later_years``` together, and store that in a variable named ```human_years```.

6. Write a ```std::cout``` statement that displays your dog’s name and age in human years.

Use chaining to display the value in the following sentence:

"My name is ____! Ruff ruff, I am [AGE] years old in human years."

You can fill in the blank with your dog’s name and ```[AGE]``` with the value of ```human_years``` in the sentence above.

You can find the source code in the [dog_years.cpp](https://github.com/keldavis/c-plus-plus-practice/blob/master/foundations/Introduction/dog_years.cpp) file.

## Quadratic Formula

In algebra, a quadratic equation is an equation having the form:

ax^2 + bx + c = 0 

Graphing, we get the curve below:

![alt text](https://s3.amazonaws.com/codecademy-content/courses/learn-cpp/variables/graph.gif)

The corresponding x values are the x-intercepts of the graph, while a, b, and c are constants.

Write a C++ program called quadratic.cpp that solves the quadratic equation for the x‘s:

![alt text](https://cdn.kastatic.org/googleusercontent/nI2riiPBcl9hZ22KKdYZGFmsVNhcKLiuwPly9l1tU5BMaqcOs9bfPKRyoGAFgK-PNpc-c7x_tNuskGdzawvy_Pza)

1. Declare 3 variables:

- a for the number a
- b for the number b 
- c for the number c

They should be able to hold decimal numbers.

2. Output this prompt for the user:

```Enter a:```

And let the user type something and save that into variable ```a```.

3. Do the same for variable ```b``` and variable ```c```.

4. Declare two variables to store the roots: 

- ```root1``` for root number one 
- ```root2``` for root number two

5. There are two roots here:

For root1, the equation has a + sign

**Note**: You can use ```std::sqrt()``` to get a number’s square root.

```std::sqrt()``` is a built-in C++ function you gain access to by including the ```<cmath>``` library at the top of the file. For example, ```std::sqrt(9)``` would be 3.

6. For ```root2```, it’s almost identical but the equation has a - sign

7. Output these values using ```std::cout```

8. Compile and execute using the terminal.

And plug in 6, -7, -3 for a, b, and c:

```
Enter a: 6
Enter b: -7
Enter c: -3
Root 1 is 1.5
Root 2 is -0.333333
```

Or try 3, -11, -4 for a, b, and c:

```
Enter a: 3
Enter b: -11
Enter c: -4
Root 1 is 4
Root 2 is -0.333333
```

Did you get the right roots?

The source code for this program is found in the [quadratic.cpp](https://github.com/keldavis/c-plus-plus-practice/blob/master/foundations/Introduction/quadratic.cpp) file.

## Piggy Bank
# A program that prompts the user for an amount of three different foreign currencies then converts them to US dollars.

1. Declare four variables:
- ```pesos```
- ```reais```
- ```soles```
- ```dollars```

2. Ask the user the first question: 

"Enter number of Colombian Pesos:"

3. Take the user's answer to the first question and store it in ```pesos```

4. Do the same for reais and soles currencies.

5. Google the conversion rates
- from Pesos to USD
- from Reais to USD
- from Soles to USD

6. Write an equation that solves for the total USD.

This will look something like:

```
dollars = (conversion_rate1 * currency1) + 
(conversion_rate2 * currency2) + 
(conversion_rate3 * currency3)
```

7. Display the total amount of USD. Your final output should look like:

"US Dollars = $______"

The source code for this program can be found in the [currency.cpp](https://github.com/keldavis/c-plus-plus-practice/blob/master/foundations/Introduction/currency.cpp) file.