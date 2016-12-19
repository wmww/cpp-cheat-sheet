# Fundamental Language Syntax

## Comments
```
// single line comment

/*
multi
line
comment
*/
```

## Variables

### Creation
```
type name;
```

### Common types
* `int`: whole number
* `double`: floating point number (numbers with a decimal point)
* `char`: a single ASCII character

Variables can also be of more complex types, like structures and classes.

## Functions

### Creation
```
//at top of file
out_type name(in_1_type in_1_name, in_2_type in_2_name);

//elsewhere
out_type name(in_1_type in_1_name, in_2_type in_2_name)
{
	//do stuff
	return out;
}
```

### Input
There can be any number of function inputs (parameters). If you don't want the function to take any input, just leave the space in between the parentheses empty.

### Outputs
A function can only have one output. If you need more, send in references or return a struct. If you don't want the function to return any output, make the output type `void` and omit the return statement.

### Function prototypes
The line at the top of the file is called a function prototype. It should be exactly the same as the function header (the line before the actual code), except that it ends with a semicolon<sup>1</sup>. You may think that writing the exact code twice is dumb, and you would be completely right. You still have to do it though, so quit complaining.

## Main
Main is a function that every program must have. It is the entry point for the program. It does not need a prototype. It should look like this:
```
int main(int argc, char** argv)
{
	// your code here
	return 0;
}
```
You can just copy this into your program. `argc` and `argv` are used for getting command line inputs, but you probably don't need them now.

## Printing

to print output, debug messages, etc., do the following:
```
// at the top of your file, above function prototypes
#include <iostream>
using std::cout;
using std::endl;

// in some function somewhere
cout << value_to_print_1 << value_to_print_2 << endl;
```
I know it makes no sense, but you will have it memorized in no time.<sup>2</sup>

## Example
```
int sumWithTen(int a, int b);

int main(int argc, char** argv)
{
	int val=sumWithTen(6, 8)
	cout << val << endl; // prints 24

	return 0;
}

int sumWithTen(int a, int b)
{
	int c=a+b
	return c+10
}
```

<sup>1</sup> Technically the parameter names in a function prototype don't have to be the same or even present, but it is good practice to include them.

<sup>2</sup> Rather then `using std::cout;` you can write `std::cout` every time you want to use `cout`, or you can just write `using namespace std;` and never have to write `std::` for anything. The problem with the former is that it is annoying and the problem with the latter is that you can get namespace collisions.
