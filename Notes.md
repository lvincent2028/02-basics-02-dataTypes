# Class Notes: An Introduction to Data Types
(Repository: _02-basics-02-dataTypes_)

A first introduction to the `char`, `bool`, `float`, `double` and `constant` data types.

## The char Data Type
In the previous activities, you were introduced to the data type known as a `string`, which is short for "string of characters". You declared strings using double quotes:
```cpp
string myString = "Notice the double quotes!"
```

In C++, the `char` data type is typically used to store a single character.
```cpp
char myChar = 'A';
```

A `char` uses 1 byte (8 bits) of storage. Characters are internally stored as numbers, using  ASCII.
The character `A`, for example is stored as the ASCII decimal value of `65` (in hexadecimal: `0x41`).

This means that a `char` can also store 8-bit,
signed integers (from `-128` to `127`, in decimal). 

### Casting
In C++, it is possible to force the bit pattern to be interpreted differently than it was declared. This is called __casting__. Since a `char` is stored as a single byte, it is possible to print that byte as an integer by casting it:
```cpp
cout << "myChar: " << (int)myChar << endl;
```
Since characters are stored as their ASCII values, casting to an integer causes the integer value to be printed.

### Initializing a char with an Integer
Since characters are stored as integers in a single byte, they can be initialized using integers:
```cpp
myChar = 75; // myChar = 'K'
```
When a character is initialized as a negative integer:
```cpp
char myChar = -1;
```
the bit pattern will be a two's complement representation of `-1`: `11111111`, which is `255` in decimal.
On many systems, this is an unprintable character because regular ASCII is only defined
from `0` to `127` (in decimal) so the system will print something that will look random.
On systems that support extended ASCII, `255` is a valid character (but can't be printed here).

## The bool Data Type
In C++, the `bool` data type has a Boolean value: `true` or `false`.

Internally, a `bool` is stored as an integer and can only take on one of two values: `0` (for `false`) and `1` (for `true`).

If a variable is declared as a `bool`, then the bit pattern representing `0` (all bits are zero) is `false`. All other bit patterns represent `true`. 

Often when a `bool` is printed, it is preferred to print the "true" or "false" strings. This can be done using the `boolalpha` ("boolean alphabetic") and `noboolalpha` ("no boolean alphabetic") __stream manipulators__, as shown in this example code:
```cpp
cout << boolalpha;
cout << true << endl; // prints true
cout << noboolalpha;
cout << true << endl; // prints 1
```

### The '!' Unary Operator
The `!` operator is the logical `NOT` (often referred to by C/C++ programmers as 'bang'): 
it turns `true` into `false` and `false` into `true`:
```cpp
cout <<  true << endl; // output: 1
cout << !true << endl; // output: 0
```

A __unary operator__ (as opposed to a binary operator) only acts on a single variable.  For many years in math, you have been using the unary minus operator `-` to make an integer negative: `-9`.

You are also very familiar with __binary operators__, which act on two variables.  The plus sign `+` is a binary operator for adding two numbers `5+6`.

## The float and double Data Types
In C/C++ there are two main types of numbers that we can work with

1. Integers: `..., -3, -2, -1, 0, 1, 2, 3, ...`
2. Decimal numbers: `3.5, -0.02, 4.3896x10^11, ...`

Decimal numbers are often call floating point numbers or just 'floats' for short. For decimal numbers, there are three basic data types in C++:
1. `float`
2. `double`
3. `long double`

The main difference between these is how many decimal places can be stored
(which is referred to as the **precision**).
`double` got its name from the fact that in the original C programming language,
a `double` used twice as many bytes as a `float`.
In today's computers, main memory is not as scarce a resource as it once was,
so we're going to mainly use `double` for our floating point numbers.

### Integer versus Floating Point Arithmetic
In the following line of code, _fraction_ (a variable declared as a `double`)
will be assigned the value 0:
```cpp
double fraction = 1/3;
```
This is because `1/3` is dividing integers: The decimal value of `0.33333...` gets **truncated** to `0`.
When you use a decimal number in the divide operation, the full precision of the machine is used:
```cpp
double fraction = 1./3;
```
It is likely that your console output only had 6 digits of precision: `0.333333`

#### CHALLENGE: Setting the output precision
To use full `double` machine precision in math operations, use:
```cpp
#include <iostream>
#include <iomanip>
#include <limits>
using namespace std;

int main(int argc, const char * argv[]) {
    cout << setprecision(numeric_limits<double>::digits10 + 1);
    cout << 1. / 3 << endl;
    return 0;
}
```
This will likely print with 16 digits of precision (the `+ 1` ensures that rounding errors are minimized and the precision is maximized).

To use the maximum machine precision in math operations, use `long double`:
```cpp
int main(int argc, const char * argv[]) {
    cout << setprecision(numeric_limits<long double>::digits10 + 1);
    cout << 1.0L / 3.0L << endl;
    return 0;
}
```
__In the real world...__ Using `long double` and setting the precision is essential
when performing scientific or financial computations where precision is crucial.

## Variables versus Constants
In C++, we can declare __variables__, assign them values and change those values as the program runs.
On the other hand, __constants__ are also values, but they cannot change as the program runs.
In the following example, the second 5.3333333333 is a constant:
```
double myVariable = 5.3333333333
cout << myVariable << endl;
cout << 5.3333333333 << endl; // <- a constant
```

We'll go deeper into this later, but for now, it's good to know that constants do not require main memory
to be allocated when the program runs, but variables do.
Later we will also learn how to define constants so that we can reference them in our code
without having to re-type the value every time we want to use it.

### The Greco Connection
In The Greco Assembly Language, you used __constants__ when you wrote:
```
LOADV    R1, 0A
```
0x0A in that line of code is a constant: it takes up space in the machine-language instruction but no
additional space in memory is allocated to it.

You used __variables__ when you wrote:
```
LOADL    R1, num1
```
`num1` in that line of code would have been __declared__ in the `.data` section, memory would have been __allocated__ for it, and it could have been __initialized__:
```
        .data
num1:          0A
```
