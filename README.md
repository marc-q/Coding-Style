# C Coding Style
Each Coding Style has its own nouances and needs its own collection of rules.
Some sections are copied from other pages (see [References](#references)) because i want to organize the rules in one file.

In this article:
* [Line Width](#line-width)
* [Indentation](#indentation)
	* [Spaces](#spaces)
	* [Braces](#braces)
* [Conditionals](#conditionals)
* [Functions](#functions)
* [Comments](#comments)
* [Namespace](#namespace)
* [Header Files](#header-files)
* [References](#references)

## Line Width
Try to use lines of code between 80 and 120 characters long.
This amount of text is easy to fit in most monitors with a decent font size.
Lines longer than that become hard to read, and they mean that you should probably restructure your code.
If you have too many levels of indentation, it means that you should fix your code anyway.

Do not eliminate whitespace and newlines just because something would fit on a single line.

## Indentation
Tabs with a length of 8 characters are used for the indentation.
Each new level is indented by a tab, braces go on a line by themselves.

*Do not ever change the size of tabs in your editor;* leave them as 8 spaces.

```C
for (int i = 0; i < 10; ++i)
{
        printf ("%i is ", i);
        
        if ((i % 2) == 0)
                printf ("even!\n");
        else
                printf ("odd!\n");
}
```

### Spaces
Put one space:
* After commas.
* Between operators.
* Before an opening parenthesis.

Remove spaces:
* In whitespace-only line.
* Between parentheses and the parameters.
* Between empty braces, and parentheses.

```C
function_a ();	// 1 space between function_a and '(', 0 space between parentheses.

if (true)	// 1 space between if and '('.
{               // 0 space after opening brace-only line.
	int i = (1 + 2) * 3;	// 1 space around '=', '+' and '*'.
	
	function_b (i, 1);	// 1 space between function_b and '(', 1 space after commas. 
}               // 0 space after closing brace-only line.
```

### Braces
* Curly braces should not be used for single statement blocks.
* Curly braces should always be placed on a new line.

```C
if (condition)
        single_line ();
else
        single_line ();
```

**The “no block for single statements” rule has only four exceptions:**
1. In GNU style, if either side of an if-else statement has braces, both sides should, to match up indentation.
2. If the single statement covers multiple lines, e.g. for functions with many arguments, and it is followed by else or else if.
3. If the condition is composed of many lines.   
*Note that such long conditions are usually hard to understand. A good practice is to set the condition to a boolean variable, with a good name for that variable. Another way is to move the long condition to a function.*
4. Nested ifs, in which case the block should be placed on the outermost if.

In general, new blocks should be placed on a new indentation level, like this:

```C
function_call_a ();
function_call_b ();

{
        const int type = 1;
        
        fwrite (&type, sizeof (type), 1, f); 
}
```

## Conditionals
`if`, `else`, `for`, `while`, and `switch` statements should be followed by a space.

```C
if (a == 8)
	...
for (;;)
{
	...
}
```

## Functions
* Functions should be declared by placing the returned value on a separate line from the function name.
* The argument list must be broken into a new line for each argument, with the argument names right aligned, taking into account pointers.
* The argument list order should be: `self`, `input`, `output`.
* While curly braces for function definitions should rest on a new line they should not add an indentation level.

```C
void
function (const int  a,
          const int  b,
          int       *sum)
{
        ...
}
```

## Comments  
* Use C++ style for single-line comments.
* Use C style for multiline comments.

```C
// TODO: One line to rule them all`.

/* A verry long comment broken
 * into two lines.
 */
```

## Namespace
* Functions should use `lower_case_with_underscores`.
* Structures, types and objects should use `CamelCaseWithoutUnderscores`.
* Macros and constants should use `UPPER_CASE_WITH_UNDERSCORES`.
* All symbols should be prefixed with a short (2–4 characters) version of the namespace. This is shortened purely for ease of typing, but should still be unique.
* All methods of a class should also be prefixed with the class name.

## Header Files
* Function definitions should be vertically aligned in three columns.
* The maximum width of each column is given by the longest element in the column.
* It is also possible to align the columns to the next tab.

```C
return_type          function_name           (type   argument,
                                              type   argument,
                                              type   argument);
```

## References
* https://developer.gnome.org/programming-guidelines/stable/c-coding-style.html.en
* https://developer.gnome.org/programming-guidelines/stable/namespacing.html.en
