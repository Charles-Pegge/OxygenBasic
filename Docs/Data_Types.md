# Oxygen Basic Data Types

### Integer Types

| Name       | Description |
| ---------- | ----------- |
| [byte](#byte) | 8-bit (1 byte) unsigned integer ranging in value from 0 to 255. |
| [sbyte](#sbyte) | 8-bit (1 byte) signed integer ranging in value from -128 to 127. |
| [ubyte](#ubyte) | 8-bit (1 byte) unsigned integer ranging in value from 0 to 255. |
| [bool](#bool) | Boolean data type. Can hold the values True or False. |
| [boolean](#boolean) | Boolean data type. Can hold the values True or False. |
| [short](#short) | 16-bit (2 bytes signed integer ranging in value from -32,768 to 32,767. |
| [long](#long) | 32-bit (4 bytes signed integer ranging in value from -2,147,483,648 to 2,147,483,647. |
| [int](#int) | 32-bit (4 bytes signed integer ranging in value from -2,147,483,648 to 2,147,483,647. |
| [integer](#integer) | 32-bit (4 bytes signed integer ranging in value from -2,147,483,648 to 2,147,483,647. |
| [word](#word) | 16-bit (2 bytes) unsigned integer ranging in value from 0 to 65,535. |
| [dword](#dword) | 32-bit (4 bytes) signed integer ranging in value from 0 to 4,294,967,295. |
| [ulong](#ulong) | 32-bit (4 bytes) signed integer ranging in value from 0 to 4,294,967,295. |
| [uint](#uint) | 32-bit (4 bytes) signed integer ranging in value from 0 to 4,294,967,295. |
| [quad](#quad) | 64-bit (8 bytes) signed integer ranging in value from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807. |
| [void](#void) | Specifies a null type. |
| [sys](#sys) | 32-bit (4 bytes) in 32-bit platforms and 64-bit (8 bytes) in 64-bit platforms. |

### Floating-point Types

| Name       | Description |
| ---------- | ----------- |
| [single](#single) | 32-bit (4 bytes) single-precision floating number ranging in value from +/- 8.43\*10^-37 to 3.40\*10^38. |
| [double](#double) | 64-bit (8 bytes) double-precision floating number ranging in value from +/- 4.19\*10^-307 to 1.79\*10^308. |
| [extended](#extended) | 10 bytes extended-precision floating number ranging in  value from +/- 3.4\*10^-4932 to 1.2\*10^4932. |
| [float](#single) | 32-bit (4 bytes) single-precision floating number ranging in value from +/- 8.43\*10^-37 to 3.40\*10^38. |

### String Types

| Name       | Description |
| ---------- | ----------- |
| [asciiz](#asciiz) | Fixed-length 8-bit null terminated string. |
| [asciiz2](#asciiz2) | Fixed-length 16-bit double null terminated string. |
| [bstr](#bstr) | Variable-length 8-bit string (a bStr is an array of ansi characters). |
| [bstring](#bstring) | Variable-length 8-bit string (a bstring is an array of ansi characters). |
| [bstring2](#bstring2) | Variable-length 16-bit string (a bstring is an array of unicode characters). |
| [char](#char) | 8-bit string (a char is an array of ansi characters). |
| [string](#string) | Variable-length 8-bit string (a string is an array of characters). |
| [string2](#string2) | Variable-length 16-bit string (a string2 is an array of unicode characters). |
| [wstring](#wstring) | Variable-length 16-bit string (a wstring is an array of unicode characters). |
| [wchar](#wchar) | 16-bit string (a wchar is an array of unicode characters). |
| [wide](#wide) | Variable-length 16-bit string (a wide string is an array of unicode characters). |
| [zstring](#zstring) | Fixed-length 8-bit null terminated string. |
| [zstring2](#zstring2) | Fixed-length 16-bit double null terminated string. |

### Modifiers

| Name       | Description |
| ---------- | ----------- |
| [long](#long) | Used in conjunction with other types to double the bit width. |
| [ptr](#ptr) | Declares a pointer variable. |
| [short](#short) | Used in conjunction with other types to halve the bit width. |
| [signed](#signed) | Specifies that the type is a signed integer. |
| [unsigned](#unsigned) | Specifies thay the type is an unsigned integer. |
| [wide](#wide) | Used in conjunction with other types to double the bit width. |

### Assembler

| Name       | Description |
| ---------- | ----------- |
| [qword](#qword) | Specifies a 64-bit operand in assembly code.  |

# <a name="byte"></a>byte

8-bit (1 byte) unsigned integer ranging in value from 0 to 255.

```
dim byteVar as byte
byteVar = 100
```

```
byte byteVar
byteVar = 100
```

```
dim as byte byteVar
byteVar = 100
```

A byte as an addressable unit of data storage large enough to hold any member of the basic character set of the execution environment. It must hold at least 256 different values, and is represented by eight bits.

# <a name="sbyte"></a>sbyte

8-bit (1 byte) signed integerr tanging in value from -128 to 127.

```
dim sbyteVar as sbyte
sbyteVar = -100
```

```
sbyte sbyteVar
sbyteVar = 100
```

```
dim as sbyte sbyteVar
sbyteVar = 100
```

A byte as an addressable unit of data storage large enough to hold any member of the basic character set of the execution environment. It must hold at least 256 different values, and is represented by eight bits.

# <a name="ubyte"></a>ubyte

8-bit (1 byte) unsigned integer ranging in value from 0 to 255.

```
dim ubyteVar as ubyte
ubyteVar = 100
```

```
ubyte ubyteVar
ubyteVar = 100
```

```
dim as ubyte ubyteVar
ubyteVar = 100
```

A byte as an addressable unit of data storage large enough to hold any member of the basic character set of the execution environment. It must hold at least 256 different values, and is represented by eight bits.

# <a name="bool"></a>bool

Boolean data type. Can hold the values true (<> 0) or false (0).

```
dim b as bool
b = true
```

```
bool b
b = true
```

```
dim as bool b
b = true
```

Notionally a boolean type, but in reality it is a long (32bit signed integer).

# <a name="boolean"></a>boolean

Boolean data type. Can hold the values true (<> 0) or false (0).

```
dim b as boolean
b = true
```

```
boolean b
b = true
```

```
dim as boolean b
b = true
```

Notionally a boolean type, but in reality it is an ubyte (8 bit unsigned integer).

# <a name="short"></a>short

16-bit (2 bytes signed integer ranging in value from -32,768 to 32,767.

```
dim n as short
n = 12345
```

```
short n
n = 12345
```

```
dim as short n
n = 12345
```

Also used in conjunction with other types to halve the bit width.

```
short long n
n = 12345
```

# <a name="long"></a>long

32-bit (4 bytes signed integer ranging in value from -2,147,483,648 to 2,147,483,647.

```
dim n as long
n = 1234567890
```

```
long n
n = 1234567890
```

```
dim as long n
n = 1234567890
```

Also used in conjunction with other types to double the bit width.

```
long short n
n = 1234567890
```

# <a name="int"></a>int

32-bit (4 bytes signed integer ranging in value from -2,147,483,648 to 2,147,483,647.

```
dim n AS int
n = 1234567890
```

```
int n
n = 1234567890
```

```
dim as int n
n = 1234567890
```

# <a name="integer"></a>integer

32-bit (4 bytes signed integer ranging in value from -2,147,483,648 to 2,147,483,647.

```
dim n as integer
n = 1234567890
```

```
integer n
n = 1234567890
```

```
dim as integer n
n = 1234567890
```

# <a name="word"></a>word

16-bit (2 bytes) unsigned integer ranging in value from 0 to 65,535.

```
dim n AS word
n = 12345
```

```
word n
n = 12345
```

```
dim as word n
n = 12345
```

If you assign a negative number to a word variable, the value is converted to an unsigned word, e.g.

```
dim n AS word
n = -1
print n
' Output: 65535
```

# <a name="dword"></a>dword

32-bit (4 bytes) signed integer ranging in value from 0 to 4,294,967,295.

```
dim n AS dword
n = 1234567890
```

```
dword n
n = 1234567890
```

```
dim as dword n
n = 1234567890
```

# <a name="ulong"></a>ulong

32-bit (4 bytes) signed integer ranging in value from 0 to 4,294,967,295.

```
dim n AS ulong
n = 1234567890
```

```
ulong n
n = 1234567890
```

```
dim as ulong n
n = 1234567890
```

# <a name="uint"></a>uint

32-bit (4 bytes) signed integer ranging in value from 0 to 4,294,967,295.

```
dim n as uint
n = 1234567890
```

```
uint n
n = 1234567890
```

```
dim as uint n
n = 1234567890
```

# <a name="quad"></a>quad

64-bit (8 bytes) signed integer ranging in value from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.

```
dim n as quad
n = 9223372036854775
```

```
quad n
n = 9223372036854775
```

```
dim as quad n
n = 9223372036854775
```

# <a name="void"></a>void

Specifies a null type.

```
void * pv = getmemory(100 * sizeof(float))
...
freememory pv
```

# <a name="sys"></a>sys

32-bit (4 bytes) in 32-bit platforms and 64-bit (8 bytes) in 64-bit platforms. To be used mainly to work with handles and opaque pointers, that are 32-bit in 32-bit systems and 64-bit in 64-bit systems. This type is always wide enough to hold a pointer.

The following example retrieves the handle of a Windows control identified by ID that is child of the Window identifield by the hwnd handle.

```
dim hCtl as sys = GetDlgItem(hwnd, ID)
```

# <a name="single"></a>single / float

32-bit (4 bytes) single-precision floating number ranging in value from +/- 8.43\*10^-37 to 3.40\*10^38. They are limited to six digiys of precision and can only accurately hold multiples of powers of two, which will lead to inaccuracies in most base-10 fractions. `single` and `float`are the same data type.

```
dim n as single
n = 123.45
```

```
single n
n = 123.45
```

```
dim as single n
n = 123.45
```

# <a name="double"></a>double

64-bit (8 bytes) double-precision floating number ranging in value from +/- 4.19\*10^-307 to 1.79\*10^308. They contain at most 53 bits of precision, or about 15 decimal digits, and can only accurately hold multiples of powers of two, which will lead to inaccuracies in most base-10 fractions.

```
dim n as double
n = 12356.789
```

```
double n
n = 12356.789
```

```
dim as double n
n = 12356.789
```

# <a name="extended"></a>extended

10 bytes (80-bit) extended-precision floating number ranging in  value from +/- 3.4\*10^-4932 to 1.2\*10^4932.

This 80-bit format uses one bit for the sign of the significand, 15 bits for the exponent field (i.e. the same range as the 128-bit quadruple precision IEEE 754 format) and 64 bits for the significand. The exponent field is biased by 16383, meaning that 16383 has to be subtracted from the value in the exponent field to compute the actual power of 2. An exponent field value of 32767 (all fifteen bits 1) is reserved so as to enable the representation of special states such as infinity and NAN (Not a Number). If the exponent field is zero, the value is a denormal number and the exponent of 2 is −16382.

```
dim n as extended
--or--
extended n
--or--
dim as extended n
n = 12356789.12
```

```
extended f = 123.45
int i at @f
string fmt(int v){ return right(hex(v,8),8) }
print fmt(i[3]and 0xffff) "  " fmt(i[2]) "  " fmt(i[1])
```

# <a name="asciiz"></a>asciiz

Fixed-length 8-bit null terminated string.

```
dim s as asciiz * 260
s = "Test string"
```

```
asciiz s * 260
s = "Test string"
```
```
dim as asciiz s * 260
s = "Test string"
```

```
dim s AS asciiz *260
s = "Test string"
dim p as asciiz ptr
@p = strptr(s)
print p
```

Indirection level 0<br>
Character width 1<br>
Length determined by null terminator byte<br>
Garbage collection not required

# <a name="asciiz2"></a>asciiz2

Fixed-length 16-bit double null terminated string.

```
dim s AS asciiz2 * 260
s = "Test string 2"
```

```
asciiz2 s * 260
s = "Test string 2"
```
```
dim as asciiz2 s * 260
s = "Test string 2"
```

Indirection level 0<br>
Character width 1<br>
Length determined by 2 null terminator bytes<br>
Garbage collection not required

# <a name="bstr"></a>bstr

Variable-length 8-bit string (a bstr is an array of ansi characters).

```
dim b as bstr = "Test string"
print b
frees b
```

```
bstr b = "Test string"
print b
frees b
```

```
dim as bstr b = "Test string"
print b
frees b
```

You must free the string with `frees` when no longer reuired.

Indirection level 1<br>
Character width 1<br>
Length given by 4 byte integer immediately before byte content<br>
Also terminated by 2 null bytes<br>
Garbage collection required

# <a name="bstring"></a>bstring

Variable-length 8-bit string (a bstring is an array of ansi characters).

```
dim b as bstring = "Test string"
print b
frees b
```

```
bstring b = "Test string"
print b
frees b
```

```
dim as bstring b = "Test string"
print b
frees b
```

You must free the string with `frees` when no longer reuired.

Indirection level 1<br>
Character width 1<br>
Length given by 4 byte integer immediately before byte content<br>
Also terminated by 2 null bytes<br>
Garbage collection required

# <a name="bstring2"></a>bstring2

Variable-length 16-bit string (a bstring is an array of unicode characters).

```
dim b as bstring2 = "Test string"
print b
frees b
```

```
bstring2 b = "Test string"
print b
frees b
```

```
dim as bstring2 b = "Test string"
print b
frees b
```

You must free the string with `frees` when no longer reuired.

Indirection level 1<br>
Character width 2<br>
Length (in bytes) given by 4 byte integer immediately before byte content<br>
Also terminated by 2 null bytes<br>
Garbage collection required

# <a name="char"></a>char

8-bit (1 byte) string. Similar to C `char`, but is not conflated with byte which is a numeric type.

```
dim c AS char[260] = "Test string"
```

```
char c[260] = "Test string"
```

```
dim as char c[260] = "Test string"
```

```
dim s as asciiz * 260 = "Test string"
char *p = strptr(s)
print p
```


If we use an offset, it will print the string from that offset until the end of the string, e.g.

```
char c = "Test string"
print c[2]
' Output "est string"
```

Indirection level 0<br>
Character width 1<br>
Length determined by null terminator byte<br>
Garbage collection not required

# <a name="string"></a>string

Variable-length 8-bit string (a string is an array of characters).

```
dim s as string = "Test string"
```

```
string s = "Test string"
```

```
dim as string s = "Test string"
```

Indirection level 2  (1 when passed byval as a parameter)<br>
Character width = 1<br>
Length given by 4 byte integer immediately before byte content<br>
Also terminated by 2 null bytes<br>
Garbage collection automatic


# <a name="string2"></a>string2

Variable-length 16-bit string (a string2 is an array of unicode characters).

```
dim s as string2 = "Test string"
```

```
string2 s = "Test string"
```

```
dim as string2 s = "Test string"
```

Indirection level 2 (1 when passed byval as a parameter)<br>
Character width 2<br>
Length given by 4 byte integer immediately before byte content<br>
Also terminated by 2 null bytes<br>
Garbage collection automatic

# <a name="wstring"></a>wstring

Variable-length 16-bit string (a wstring is an array of unicode characters).

```
dim ws as wstring = "Test string"
```

```
wstring ws = "Test string"
```

```
dim as wstring ws = "Test string"
```

Indirection level 2 (1 when passed byval as a parameter)<br>
Character width 2<br>
Length given by 4 byte integer immediately before byte content<br>
Also terminated by 2 null bytes<br>
Garbage collection automatic

# <a name="wchar"></a>wchar

16-bit (2 bytes) string.

```
dim c as wchar[260] = Test string"
```

```
wchar c[260] = Test string"
```

```
dim as wchar c[260] = Test string"
```

```
uses corewin
dim cmdline AS wchar ptr
@cmdline = GetCommandLineW
print cmdline
```

If we use an offset, it will print the string from that offset until the end of the string, e.g.

```
wchar c = "Test string"
print c[2]
' Output "est string"
```

Indirection level 0<br>
Character width 2<br>
Length determined by 2 null terminator bytes<br>
Garbage collection not required

# <a name="wide"></a>wide

Variable-length 16-bit string (a wide string is an array of unicode characters).

```
dim ws as wide = "Test string"
```

```
wide ws = "Test string"
```

```
dim as wide ws = "Test string"
```

Also used in conjunction with other types to double the bit width.

```
wide char wc
wide float wf   ' a double precision float
```

# <a name="zstring"></a>zstring

Fixed-length 8-bit null terminated string.

```
dim zs as zstring * 260 = "Test string"
```

```
zstring * 260 zs = "Test string"
```

```
dim as zstring zs = "Test string"
```

Indirection level 0<br>
Character width 1<br>
Length determined by null terminator byte<br>
Garbage collection not required

# <a name="zstring2"></a>zstring2

Fixed-length 16-bit double null terminated string.

```
dim zs AS zstring2 * 260 = "Test string"
```

```
zstring2 * 260 zs = "Test string"
```

```
dim as zstring2 zs = "Test string"
```

Indirection level 0<br>
Character width 2<br>
Length determined by 2 null terminator bytes<br>
Garbage collection not required

# <a name="qword"></a>qword

Specifies a 64 bit operand in assembly code.

```
fld qword d
```

# <a name="signed"></a>signed

Specifies that the type is a signed integer.

```
signed int v
```

A signed int (long) called v is created.

# <a name="unsigned"></a>unsigned

Specifies that the type is an unsigned integer.

```
unsigned long v
```

An unsigned long (dword) called v is created.

# <a name="ptr"></a>ptr

Declares a pointer variable.

```
' Create the pointer.
Dim p As Integer Ptr
' Create an integer value that we will point to using pointer "p"
Dim num As Integer = 98845
' Point p towards the memory address that variable "num" occupies.
@p = @num
' Print the value stored in memory pointed to by pointer "p"
print p   ' output: 98845
```
```
dim s as asciiz * 260 = "Test string"
dim p as asciiz ptr
@p = strptr(s)
print p   ' output: "Test string"
```
