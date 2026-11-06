# Assignment: 02-basics-02-dataTypes
A first introduction to the `char`, `bool`, `float`, `double` and `constant` data types.

### 0. Get Started
You will always do these two steps:
1. Launch Xcode and clone this repository.
2. Update the comment header with your name/date.

### 1. Print a _char_ Data Type
#### Preliminary Note
In C++, the `char` data type is typically used to store a single character.

#### Steps
Edit your code so that the main body is similar to the following, and then build/run it:
```
int main(int argc, const char * argv[]) {

    char myChar = 'A';
    cout << "myChar: " << myChar << endl;
    return 0;

}
```

__\*\*Commit/Push to GitHub\*\*__ with commit message that matches the section heading: _1. Print a character data type_.


### 2. Exploring Characters as Integers
#### Preliminary Note
A `char` uses 1 byte (8 bits) of storage. In C++, characters are stored as numbers, using  ASCII.
This means that the `char` data type can also store 8-bit, __signed__ integers (from –128 to 127, in decimal).

#### Steps
Before the `return 0;` statement, add the following line of code and then run your program:
```
cout << "myChar: " << (int)myChar << endl;
```
$$\large{{\text{\color{red}In Desmos, respond to Prompt 1 on Screen 2}}}$$

You were introduced to the the 'line feed' character, `\n`, earlier.  You can determine its ASCII value in the same way. Add the following line of code to your program and run it:
```
cout << "linefeed = " << (int)'\n' << endl;
```
$$\large{{\text{\color{red}In Desmos, respond to Prompt 2 on Screen 2}}}$$

We can also set a `char` value using integers. Add the following code to your program and run it:
```
myChar = 75;
cout << "myChar = " << myChar << endl;
```
$$\large{{\text{\color{red}In Desmos, respond to Prompt 3 on Screen 2}}}$$

What happens when a negative integer is used?  Add the following code to your program and run it:
```
myChar = -1;
cout << "myChar = " << myChar << endl;
```
$$\large{{\text{\color{red}In Desmos, respond to Prompt 4 on Screen 2}}}$$

__\*\*Commit/Push to GitHub\*\*__ with commit message that matches the section heading: _2. Exploring characters as integers_.

### 3. Print a _boolean_ Data Type
Before the `return 0;` statement, add the following lines of code to declare and print a `bool` data type,
and then buid/run your code:
```
bool b = true;
cout << "b = " << b << endl;
```
$$\large{{\text{\color{red}In Desmos, respond to Prompt 1 on Screen 3}}}$$

Add the following code and run it:
```
b = -76;
cout << b << endl;
```
$$\large{{\text{\color{red}In Desmos, respond to Prompt 2 on Screen 3}}}$$

Often we prefer to actually print "true" or "false" rather than "0" or "1".
To do this we use `boolalpha` ("boolean alphabetic") and `noboolalpha` ("no boolean alphabetic").
Add the following code to your program, run it, and be sure to understand the output.
```
bool b1 = 0;
cout << boolalpha;
cout << b1 << endl;
bool b2 = 1;
cout << noboolalpha;
cout << b2 << endl;
```

__\*\*Commit/Push to GitHub\*\*__ with commit message that matches the section heading:
_3. Print a boolean data type_.

### 4. Print 'true' Versus 'not true'
Before the `return 0;` statement, add the following lines of code and run your code:
```
cout << "'true' = " << true << endl;
cout << "'!true' = " << !true << endl;
bool b2 = true;
cout << "b2 = " << b2 << endl;
cout << "!b2 = " << !b2 << endl;
```
$$\large{{\text{\color{red}In Desmos, respond to Prompt 1 on Screen 4}}}$$

__\*\*Commit/Push to GitHub\*\*__ with commit message that matches the section heading:
_4. Print 'true' versus 'not true'_.

### 5. Decimal Numbers
#### Preliminary Note
In C/C++ there are two main types of numbers that we can work with

1. Integers: $${\dots,\ -3,\ -2,\ -1,\ 0,\ 1,\ 2,\ 3,\ \dots}$$
2. Decimal numbers: $${3.5,\ -0.02,\ 4.3896\times10^{-11},\ ...}$$

Decimal numbers are often call floating point numbers or just __floats__ for short.

#### Steps
Before the `return 0;` statement, add the following lines of code, run your code, and observe the output:

```
int age = 20;
cout << age << endl;
```

Next, edit your code to match the code below and run it.
```
int age = 20.8;
cout << age << endl;
```
$$\large{{\text{\color{red}In Desmos, respond to Prompt 1 on Screen 5}}}$$

__\*\*Commit/Push to GitHub\*\*__ with commit message that matches the section heading.

### 6. Precision: _float_, _double_, and _long double_ Data Types
#### Preliminary Note
For decimal numbers, there are three basic data types in C++:

1. `float`
2. `double`
3. `long double`

The main difference between these two data types is how many decimal places can be stored (which is referred to as the __precision__). `double` got its name from the fact that in the original C programming language, a `double` used twice as many bytes as a `float`.

#### Steps
Before the `return 0;` statement, add the following code and run your program:
```
double fraction = 1/3;
cout << fraction << endl;
double fraction2 = 1./3;
cout << fraction << endl;
```
$$\large{{\text{\color{red}In Desmos, respond to Prompt 1 on Screen 6}}}$$

__\*\*Commit/Push to GitHub\*\*__ with commit message that matches the section heading.


### 7. Variables versus Constants
Before the `return 0;` statement, add the following code and run your program:
```
double myVariable = 5.3333333333
cout << "myVariable = " << myVariable << endl;
cout << "myConstant = " << 5.3333333333 << endl;
```

__\*\*Commit/Push to GitHub\*\*__ with commit message that matches the section heading.

#### End Note
In C++, we can declare __variables__, assign them values and change those values as the program runs. On the other hand, __constants__ are also values, but they cannot change as the program runs. In the above example, the second 5.3333333333 is a constant.

### 8. Wrap Up
You will always do these two steps:
1. Double-check you have properly committed/pushed all steps (view your change history on GitHub).
2. Read the _Notes.md_ and summarize the main points in your composition book.
