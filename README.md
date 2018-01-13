# Coding-Style
This is my coding style.

Some sections are copied from other pages (see [References](#references)) i intend to stick to this file rather than linking to those pages. Not only could they change but this way im also able to customize the rules.

In this article:
* [Line Width](#line-width)
* [Indentation](#indentation)
* [Tab Characters](#tab-characters)
* [Namespace](#namespace)
* [Braces](#braces)
* [Functions](#functions)
* [Whitespace](#whitespace)
* [References](#references)

## Line Width
Try to use lines of code between 80 and 120 characters long. This amount of text is easy to fit in most monitors with a decent font size. Lines longer than that become hard to read, and they mean that you should probably restructure your code. If you have too many levels of indentation, it means that you should fix your code anyway.

## Indentation
I like to use the Linux Kernel style for indentation.
Tabs with a length of 8 characters are used for the indentation. Normaly K&R brace placing is used, but i replaced that with my own.

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

## Tab Characters
*Do not ever change the size of tabs in your editor;* leave them as 8 spaces.

## Namespace
* Functions should use `lower_case_with_underscores`.
* Structures, types and objects should use `CamelCaseWithoutUnderscores`.
* Macros and constants should use `UPPER_CASE_WITH_UNDERSCORES`.
* All symbols should be prefixed with a short (2–4 characters) version of the namespace. This is shortened purely for ease of typing, but should still be unique.
* All methods of a class should also be prefixed with the class name.

## Braces
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

## Whitespace
* Always put a space before an opening parenthesis but never after.
* Do not eliminate whitespace and newlines just because something would fit on a single line.

```C
// Valid
if (condition)
        function_a ();

// Valid
switch (condition)
{
        ...
}
```

## References
* https://developer.gnome.org/programming-guidelines/stable/c-coding-style.html.en
* https://developer.gnome.org/programming-guidelines/stable/namespacing.html.en
