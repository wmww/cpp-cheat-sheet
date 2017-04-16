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

## Strings
A string is a list of characters. A string can be 0 characters long all the way up to the size of a book (probably longer, I've never tried).

### Includeing them

To use strings in your program put this at the top:
```
#include <string>
using std::string;
```
And then, just make a variable of type string.

### string literals

A string literal is simply a number of characters surounded by quotes. You can use a string literal to set a string, or print it out directly. Here is an example:
```
string myString="hello world";
cout << myString << "!" << endl;
```

### concatination

You can combine two strings with the `+` operator. This is called concatination. For example, the following will print "hello world!"
```
string a="hello"
string b="world"
string c=a+" "+b;
cout << c+"!" << endl;
```

Note: concatinating only string literals doesn't work. At least one of the strings must be a string variable.

### converting numbers to strings

To convert a number to a string, all you need to do is put `using std::to_string` below where you include string, and then write `to_string(your_number)`. You can then concatinate it with others strings.

## Arrays

There are two completely different ways to use arrays in C++. The C style has by far the simplest syntax, but it has the huge limitation of needing a size specified at compile time. Using the C++ way, the size can change as the program runs, and as such it is what I recomend almost always and it is the only style I will show here.

### Vector
A C++ dynamically sized array is called a vector<sup>vector</sup>. To create one, do the following:
```
// at the top of the file
#include <vector>
using std::vector;

// in a function somewhere
vector<item_type> array_name; // create an array that contains 0 elements
```

### common operations
There are a number of functions you can call on a vector to do different things. Here are some of the most common ones. See the example to see exactly how they are used.
* `push_back(item)`: append an item to the end


## Namespaces

A namespace is a number of variables and functions that are grouped under a specific name. The most common namespace you will have to use is the standard namespace, called `std`. To use something in a namespace, write `namespace_name::thing_in_namespace`. For example, to print something you use `std::cout`. Writing `std::` everywhere can get a bit agrivating though, so instead you can put `using namespace std;` at the top of the file and never have to use `std::`. The problem with that You may accedentally name something of your own the same as something in the standard library, thus causing a namespace collision. A good compromise is to make the `std::` implicit on only the specific things you need to use a lot. To do this write `using namespace_name::thing_in_namespace;`. This is what I do in most of my examples.

# Examples

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

<sup>2</sup> The line `using std::cout;` has to do with namespaces. There are a few alternitives, but I think this style is best.

<sup>vector</sup> Please see my oppinion on the name 'vector' here: [](bit.ly/2hAVet7)
