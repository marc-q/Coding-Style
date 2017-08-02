# Coding-Style
Working on my coding style.

## Indentation

## Tab Characters
Do not ever change the size of tabs in your editor; leave them as 8 spaces.

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

## References
* https://developer.gnome.org/programming-guidelines/stable/c-coding-style.html.en
