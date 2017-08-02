# Coding-Style
This is my coding style.

Some sections are copied from other pages (see [Reference](https://github.com/marc-q/Coding-Style/tree/c_rules#references)) i intend to stick to this file rather than linking to theese pages. Not only could they change but this way im also able to customize the rules.

## Indentation

## Tab Characters
*Do not ever change the size of tabs in your editor;* leave them as 8 spaces.

## Braces
Curly braces should not be used for single statement blocks: 

```C
// Valid
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
// Valid
int
function (int a)
{
        ...
}
```

```C
// Invalid
int
function (int a) {
        ...
}

// Invalid
int function (int a)
{
        ...
}

// Invalid
int function (int a) {
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

```C
// Invalid
if(condition)
        function_a ();

// Invalid
switch ( condition )
{
        ...
}
```

## References
* https://developer.gnome.org/programming-guidelines/stable/c-coding-style.html.en
