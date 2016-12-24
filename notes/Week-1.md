---
title: 'Week 1'
author: 'Aryaman Arora'
date: 'September 2016'
output:
  tufte::tufte_html:
    highlight: pygments
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(eval=FALSE)
```

## C

Some new concepts for C:

- **source code** - the code that you write
- **object code** - the code that the computer understands, in binary
- **compiler** - software that takes source code and spits out object code

### Functions

#### hello.c

```{c}
##include <stdio.h>

int main(void) // when green flag clicked
{
	printf("hello, world\n"); // say hello world
}
```

`main` is the main part of our program; the main function. The curly braces enclose the "meat" of our function. `printf` is equivalent to the `say` block in Scratch.

To run this code, you do this. The first part compiles the code, while the second part runs it.

```bash
$ make hello
$ ./hello
hello, world
```

#### Loops

Forever loops in Scratch are while-loops in C. This prints "hello, world" forever.

While-loops execute while a condition is true, and since we passed the boolean "true", it will execute forever.
```{c}
while (true) // forever
{
	printf("hello, world\n");
}
```

You can also repeat with a "counter" variable. This prints "hello, world" 10 times:
```{c}
for (int i = 0; i < 10; i++) // repeat 10
{
	printf("hello, world\n");
}
```

#### Variables

```{c}
int counter = 0; // set counter to 0
while (true) //forever
{
	printf("%i\n", counter); // say counter
	counter++; // increment counter
}
```

A variable stores a value, just like in Scratch. We say `int counter = 0` because we want to specify that it is an integer.

The `%i` acts as a placeholder for an integer.

#### Booleans

```{c}
(x < y);
((x < y) && (y < z));
```

Boolean expressions are easy too.

#### Conditions

```{c}
if (x < y)
{
	printf("x is less than y\n");
}
else if (x > y)
{
	printf("x is greater than y\n");
}
else
{
	printf("x is equal to y\n");
}
```

So are conditions.

## Writing Code
The actual programming will be done on CS50 IDE, a cloud based programming environment. It is accessible at http://cs50.io/.

### Libraries
In our examples, `stdio.h` is a library of important functions like `printf`. We include it like this:

```{c}
##include <stdio.h>
```

There are other libraries as well, like `cs50.h` (which include the data type `string`) and `stdlib.h` and `math.h`.

### Compiling
When we use `make` in the terminal, we actually called something else. In our case, `clang` is what compiles C code. So,

```{bash}
clang hello.c
```
is similar to
```{bash}
make hello
```
except it will output to `a.out`.

## Appendix

### Kinds of Data
-  `string` - plain text (only in cs50.h)
-  `char` - a single byte (character)
-  `float` - a 32-bit number
-  `double` - a 64-bit number
-  `int` - integer, generally 32 bits
-  `long long` - 64 bit integer
-  `bool` - true or false (only cs50.h)

#### Format codes
- `%c`
- `%s`
- `%f`
- `%i`
- `%lld`
- `%s`

### Escape sequences
To print some special characters.

- `\n` - new line
- `\t` - tab character
- `\r` -
- `\"` - double quote

### Functions

- `GetChar, GetDouble, GetFloat, GetInt, GetLongLong, GetString` - prompts the user for information; these have error checking
- `printf` - print out text for the user to see

### Loops

- `for` - for some condition, do this
- `while` - while something is happening
- `do ... while ...` - do something check after while something else is true

### Variables

- `int, char` etc. - initialize a variable named ...
- `... = ...` - set a variable to something
- `... == ...` - check if two things are equal