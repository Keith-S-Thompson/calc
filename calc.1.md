# NAME

calc - Text-mode RPN calculator

# SYNOPSIS

calc \[options\]

    Options:
       -help   Show short usage message
       -help1  Show medium usage message
       -help2  Show long usage message
       -man    Show long usage message (invokes pager)

       -[no]readline Use Perl::ReadLine for input (default if available)
       -debugging    Debugging (developer option)

# DESCRIPTION

**calc** is a text-mode RPN calculator

Operands and commands may be entered as text or as command-line arguments.
Multiple command may be entered on a line.

# OPTIONS

- **-help**

    Show short usage message

- **-help1**

    Show medium usage message

- **-help2**

    Show long usage message

- **-man**

    Show long usage message using **perldoc**, invokes pager

- **-\[no\]readline**

    Use `Perl::ReadLine` for input (enabled by default if available)

- **-debugging**

    Enable debugging (developer option)

# COMMANDS AND OPERANDS

- **?, help**

    Show help message

- **man**

    Show man page (like `calc -man`)

- **number**

    Push a number onto the stack

    The number may be integer (decimal or hexadecimal) or floating-point.

- **num:num:...**

    Push a number in HH:MM:SS format (base 60)

- **I:number**

    Push a BigInt on the stack

- **B:number**

    Push a BigFloat on the stack

- **&lt;num>\_&lt;unit>**

    num \* unit, where &lt;unit> can be any variable name

    Anything not recognized as a number or command is pushed onto the
    stack as a string.

- **+, -, \*, /, %, \*\***

    Arithmetic operators

- **--**

    Negate

- **//**

    Reciprocal

- **%%**

    Push quotient and remainder

- **& | ^ ~ << >>**

    Bitwise operators

- **sumn**

    Sum of top **TOS** stack elements

    For example **10 20 30 3 sumn** yields **30**

- **dup**

    Duplicate TOS (top of stack)

- **drop**

    Drop TOS

- **dropn**

    Drop **TOS+1** items from stack

- **pick**

    Nth stack element; **1 pick** is equivalent to &lt;dup>

- **depth**

    Push stack depth

- **clear**

    Clear stack; equivalent to **depth dropn**

- **swap**

    Swap top two stack elements

- **sin, cos, tan, asin, acos, atan**

    Trigonometric functions (in radians)

- **atan2**

    **atan(y/x)**

- **deg**

    Convert degrees to radians

- **rad**

    Convert radians to degrees

- **exp**

    **e\*\*x**

- **ln, loge**

    log base **e**

- **log, log10**

    log base 10

- **lg, log2**

    log base 2

- **int**

    Integer part (truncate towards 0)

- **frac**

    Fractional part

- **srand**

    Set random seed

- **srandx**

    Set random seed to specified value

- **rand**

    Random number between 0.0 and 1.0

- **sqrt**

    Square root

- **hhmm**

    Current time in minutes since midnight.

    **hhmm hms** shows the time in human-readable form.

- **vars**

    Show all variables

- **&lt;name>=**

    Assign variable

    For example **42 answer=** assigns the value **42** to the variable **answer**

- **ofmt=**

    Show output format (default is `"%.16g"`)

- **ofmt=&lt;fmt>**

    Set output format

- **.** (dot)

    Display TOS (top of stack)

- **hex**

    Display TOS in hexadecimal

- **octal**

    Display TOS in octal

- **hms**

    Display TOS in H:M:S format (base 60) (currently limited to integers)

- **comma**

    Display TOS with commas, e.g., `"12,345,678.901234"`

- <,> (comma character)

    Dump stack

- **Hex**

    Dump stack in hexadecimal

- **Octal**

    Dump stack in octal

- **HMS**

    dump stack in H:M:S format (base 60)

- **Comma**

    Dump stack with commas

- **\\**

    Inhibit stack dump

- **: ...**

    Evaluate Perl expression (one line only)

- **(...)**

    Evaluate Perl expression (no whitespace)

# PREDEFINED VARIABLES

- **pi**

    3.141592653589793

- **e**

    2.718281828459045 (Euler's constant)

- **phi**

    1.618033988749895 (golden ratio)

- **K**, **M**, **G**, **T**, **P**, **E**, **Z**, **Y**

    Metric prefixes (decimal), 1000, 1000000, ...

    kilo, mega, giga, tera, peta, exa, zetta, yotta

- **Ki**, **Mi**, **Gi**, **Ti**, **Pi**, **Ei**, **Zi**, **Yi**

    Metric prefixes (binary), 1024, 1048576, ...

    kibi, mebi, gibi, tebi, pebi, exbi, zebi, yobi

- **hundred**

    100

- **thousand**, **million**, **billion**, **trillion**, **quadrillion**, **quintillion**, **sextillion**, **septillion**, **octillion**, **nonillion**, **decillion**, **undecillion**, **duodecillion**, **tredecillion**, **quattuordecillion**, **quindecillion**, **sexdecillion**, **septendecillion**, **octodecillion**, **novemdecillion**, **vigintillion**

    Powers of 1000

# SOURCE

[https://github.com/Keith-S-Thompson/calc](https://github.com/Keith-S-Thompson/calc)

# AUTHOR

Keith Thompson <Keith.S.Thompson@gmail.com>
