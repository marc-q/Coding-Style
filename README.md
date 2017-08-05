# Coding-Style
This is my coding style.

Some sections are copied from other pages (see [References](#references)) i intend to stick to this file rather than linking to those pages. Not only could they change but this way im also able to customize the rules.

In this article:
* [Line Width](#line-width)
* [Indentation](#indentation)
* [Tab Characters](#tab-characters)
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

## Braces
Curly braces should not be used for single statement blocks: 

```C
if (condition)
        single_line ();
else
        single_line ();
```

In general, new blocks should be placed on a new indentation level, like this: 

```C
function_call_a ();
function_call_b ();

{
        const int type = 1;
        
        fwrite (&type, sizeof (type), 1, f); 
}
```

Curly braces should always be placed on a new line.   
For function definition they should not add an indentation level:

```C
int
function (int a)
{
        ...
}
```

## Functions
* Functions should be declared by placing the returned value on a separate line from the function name.
* The argument list must be broken into a new line for each argument, with the argument names right aligned, taking into account pointers.

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
Always put a space before an opening parenthesis but never after:

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
