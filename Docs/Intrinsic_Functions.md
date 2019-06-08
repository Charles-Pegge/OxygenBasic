# Oxygen Basic Intrinsic Functions

### String Functions

| Name       | Description |
| ---------- | ----------- |
| [asc](#asc) | Returns the corresponding ASCII or Unicode integer representation of a character in a string. |
| [chr](#chr) | Returns a string of characters from one or more ASCII integer values. |
| [comparestr](#comparestr) | Assembler. String comparator. It sets the CPU zero and sign flags. |
| [frees](#frees) | Deallocates a bstring. |
| [hex](#hex) | Returns the hexadecimal string representation of integer part of a number. |
| [instr](#instr) | Locates the first occurrence of a substring or character within a string. |
| [lcase](#lcase) | Returns a lower case copy of a string. |
| [left](#left) | Returns the leftmost substring of a string. |
| [len](#len) | Returns the length of a string in characters. |
| [ltrim](#ltrim) | Removes spaces on the left side of a string. |
| [mid (function)](#mid) | Returns a part of a string. |
| [mid (statement)](#mid2) | Overwrites part of a string with another string. |
| [news](#nws) | Allocates a bstring of null characters given the length in bytes.  |
| [nuls](#nuls) | Returns a string consisting of a specified number of null (chr(0)) characters. |
| [right](#right) | Returns the rightmost substring of a string. | |
| [rtrim](#rtrim) | Removes spaces on the right side of a string. |
| [space](#space) | Returns a string consisting of a specified number of spaces. |
| [str](#str) | Returns the string representation of a number. |
| [ucase](#ucase) | Returns an uppercase copy of a string. |
| [unic](#unic) | Returns the corresponding Unicode integer representation of a character in a string. |
| [val](#val) | Converts a string to a numeric value. |
| [wchr](#wchr) | Returns a wide string of characters from one or more integer values. |

### Math Functions

| Name       | Description |
| ---------- | ----------- |
| [abs](#abs) | Returns the absolute value of a number (removes the negative sign). |
| [acos](#acos) | Returns the arccosine of a number. |
| [asin](#asin) | Returns the arcsine of an number. |
| [atan](#atan) | Returns arctangent of a ratio. |
| [atn](#atn) | Returns arctangent of a number. |
| [ceil](#ceil) | Rounds a float number upward. |
| [cos](#cos) | Returns the cosine of an angle of *x* radians. |
| [deg](#deg) | Converts radians to degrees. |
| [floor](#floor) | Rounds a float number downward. |
| [frac](#frac) | Returns the fractional part of a number. |
| [hypot](#hypot) | Returns the hypotenuse (longest side) of a right angle triangle given the other 2 sides. |
| [lin](#lin) | Returns the logarithm of the first value to base e (2.71828182845904523536…). |
| [log](#log) | Returns the natural logarithm of a given number. |
| [log2](#log2) | Returns the binary (base-2) logarithm of a number. |
| [log10](#log10) | Returns the common (base-10) logarithm of a number. |
| [logn](#logn) | Returns the logarthm of the first value to the base of the second value. |
| [mod](#mod) | Returns the remainder of first value divided by the second value.  |
| [pi](#pi) | Returns pi, the ratio of the circumference of a circle to its diameter. |
| [pow](#pow) | Returns the value of the first value raised to the power of the exponent. |
| [rad](#rad) | Converts from degrees to radians. |
| [recip](#recip) | Returns the reciprocal of a value. |
| [round](#round) | Returns the integral value that is nearest to the passed float number. |
| [sgn](#sgn) | Returns the sign part of a number. |
| [sin](#sin) | Returns the sine of an angle. |
| [sqr](#sqr) | Returns the square root of a number. |
| [sqrt](#sqr) | Returns the square root of a number. |
| [tan](#tan) | Returns the tangent of a value given in radians. |
| [trunc](#trunc) | Rounds a float number towards zero. |

### Bit Manipulation Functions

| Name       | Description |
| ---------- | ----------- |
| [hibyte](#hibyte) | Returns the high-order byte of an integer value (bits 8..15). |
| [lobyte](#lobyte) | Returns the low-order byte of an integer value (bits 0..7). |
| [hiword](#hiword) | Returns the high-order word of an integer value (bits 16..31). |
| [loword](#loword) | Returns the low-order word an integer value (bits 0..15). |

### Memory Functions

| Name       | Description |
| ---------- | ----------- |
| [copy](#copy) | Copies a block of memory. |
| [copyn](#copy) | Copies a block of memory. |
| [copy0](#copy0) | Copies a null terminated string to another location. |
| [copy00](#copy00) | Copies a null terminated string of wide (2 bytes) characters to another location. |
| [freememory](#freememory) | Frees a previously allocated memory block. |
| [getmemory](#getmemory) | Allocates a block of memory and returns its base address. |

# <a name="asc"></a>asc

Returns the corresponding ASCII or Unicode integer representation of a character in a string.

The function returns zero (0) if the string is a zero length string, position is less than one (1), or position is greater than the number of characters in the string.

```
dim a as long
a = asc("ABCDEF", 2)
' Output: 66 (character "B")
```

# <a name="abs"></a>abs

Returns the absolute value of a number (removes the negative sign).

```
dim d as double
d = abs(-2.5)
' Output: 2.5
```

# <a name="chr"></a>chr

Returns a string of characters from one or more ASCII integer values

```
dim s as string
s = chr(65)
print s   ' Output "A"
s = chr(66, 67)
print s   ' Output: "AB"
```

# <a name="comparestr"></a>comparestr

Assembler. String comparator. It sets the CPU zero and sign flags: jg = greater, jl = less, jz = equal.

```
string a = "abc"
string b = "abc"
string c = "123"
sys cm
comparestr(a,b)
(
  jnz exit
  print "equal"
  jmp fwd ncompare
)
(
  jg exit
  print "less"
  jmp fwd ncompare
)
(
  jl exit
  print "greater"
  jmp fwd ncompare
)
.ncompare
```

# <a name="frees"></a>frees

Frees a bstring.

```
dim b as bstring
b = news(1000)
'...
frees b
```

# <a name="hex"></a>hex

Returns the hexadecimal string representation of integer part of a number.

| Parameter  | Description |
| ---------- | ----------- |
| *number* | A number or expression evaluating to a number. A floating-point number will be converted to integer. |
| *digits* | Optional number of digits to return. |

```
print hex(14)        ' result 'E'
print hex(14.4)      ' result 'E'
print hex(14.4, 4)   ' result '000E'
```

# <a name="instr"></a>instr

Locates the first occurrence of a substring or character within a string.

| Parameter  | Description |
| ---------- | ----------- |
| *start* | Optional. The position in *s* at which the search will begin. The first character starts at position 1. |
| *s* | The string to be searched. |
| *substring* | The substring to find. |

```
dim p as long
p = instr("abcdef abcdef","def")
' Returns: 4
```
```
dim p as long
p = instr(8, "abcdef abcdef","def")
' Returns: 11
```

#### Return Value

The position of the first occurrence of substring in *s*. Zero (0) is returned if: either substring is not found, either *s* or substring are empty strings, or *start* < 1.

# <a name="lcase"></a>lcase

Returns a lower case copy of a string.

```
dim s as string = lcase("ABCDEF")
' Output: "abcdef"
```

# <a name="left"></a>left

Returns the leftmost substring of a string

| Parameter  | Description |
| ---------- | ----------- |
| *s* | The source string. |
| *n* | The number of characters to return from the source string. |

```
dim s a string = left("abcdef", 3)
' Output: "abc"
```

# <a name="len"></a>len

Returns the length of a string in characters.

```
print len("Hello")
' Output: 5
```

# <a name="ltrim"></a>ltrim

Removes spaces on the left side of a string.

```
dim s as string = ltrim "   abc"
' Output: "abc"
```

# <a name="mid"></a>mid (function)

Returns a part of a string.

| Parameter  | Description |
| ---------- | ----------- |
| *s* | The source string. |
| *start* | The start position in *s* of the substring. The first character starts at position 1. |
| *n* | The substring length, in characters. |

If *n* is omitted or bigger than the remaining characters in the string, all remaining characters are returned. If there are no characters at the *start* position, an empty string is returned.
 
```
dim s as string
s = mid("abcdef", 3)
' Output: "cdef"
```
```
dim s as string
s = mid("abcdef", 3, 2)
' Output: "cd"
```

# <a name="mid2"></a>mid (statement)

Overwrites part of a string with another string.

| Parameter  | Description |
| ---------- | ----------- |
| *s* | The source string. |
| *start* | The start position in *s* of the substring. The first character starts at position 1. |
| *expression* | The replacement string. |

```
DIM s as string = "1234567890"
mid(s, 2) = "000"
print s   ' Output: "1000567890"
```

Alternate syntax:

```
DIM s as string = "1234567890"
mid(s, 2, "000")
print s   ' Output: "1000567890"
```

The encoding (ansi or unicode) of the assigned string must match the encoding of the target string.

This will work because both the target and the assignment are unicode:

```
dim s as string2 = "1234567890"
dim s2 as string2 = "000"
mid(s, 2) = s2
print s   ' Output: "1000567890"
```

But this won't because the literal is interpreted as an ansi string:

```
dim s as string2 = "1234567890"
mid(s, 3) = "000"
```

Contrarily to other dialects, it has not an optional *end* parameter to limit the number of characters that can be replaced (the length of the replacement string is used to calculate them). The length of the source string does not change, so if *expression* is too big, only the number of characters that fit in the source string are copied.

# <a name="news"></a>news

Allocates a bstring of null characters given the length in bytes.

```
dim b as bstring
b = news(1000)
'...
frees b
```

# <a name="nuls"></a>nuls

Returns a string consisting of a specified number of null (chr(0)) characters.

```
s = nuls(1000)
```

For wide strings, use string(n, wchr(0)) instead.

# <a name="right"></a>right

Returns the rightmost substring of a string

| Parameter  | Description |
| ---------- | ----------- |
| *s* | The source string. |
| *n* | The number of characters to return from the source string. |

```
dim s a string = right("abcdef", 3)
' Output: "def"
```

# <a name="rtrim"></a>rtrim

Removes spaces on the right side of a string.

```
dim s as string = rtrim("abc   ")
' Output: "abc"
```

# <a name="space"></a>space

Returns a string consisting of a specified number of spaces.

```
dim s as string = space(10)
' Output: "          "
```

# <a name="str"></a>str

Returns the string representation of a number.

| Parameter  | Description |
| ---------- | ----------- |
| *number* | A number or expression evaluating to a number. A floating-point number will be converted to integer. |
| *decdigits* | Optional number of decimal places to return. Rounding is automatically applied before decimal places are truncated. |

```
dim s as string
s = str(-1.23456)     ' result: -1.23456
s = str(-1.23456, 3)   ' result: -1.235
```

# <a name="ucase"></a>ucase

Returns a lower case copy of a string.

```
dim s as string = ucase("abcdef")
' Output: "abcdef"
```

# <a name="unic"></a>unic

Returns the corresponding Unicode integer representation of a character in a string.

The function returns zero (0) if the string is a zero length string, position is less than one (1), or position is greater than the number of characters in the string.

```
dim s as string2 = "ABCDEF"
dim c as long = unic(s, 2)
' Output: 66 (character "B")
```

# <a name="val"></a>val

Converts a string to a numeric value.

```
dim v as double = val(val "2.5")
' Output: 2.5
```

The function parses the string from the left, skipping any white space, and returns the longest number it can read, stopping at the first non-suitable character it finds. Scientific notation is recognized, with "D" or "E" used to specify the exponent.

```
dim b as double = Val("2.1E+30xa211")
```

`val` can be used to convert integer numbers in binary / octal / hexadecimal format, if they have the relevant identifier ("&B" / "&O" / "&H") prefixed, for example: val("&HFF") returns 255.

```
print val("&B11100101")
```

# <a name="wchr"></a>wchr

Returns a wide string of a 2 byte character (encoding 0..65535 / 0xffff)

```
wstring ws = wchr(65)   ' result: "A"
```

# <a name="acos"></a>acos

Returns the arccosine of a number. The result is within the range of 0 to Pi. `acos`is the inverse of the `cos` function. The returned angle is measured in radians (not degrees).

```
dim d as double
d = acos(0.5)
```

# <a name="asin"></a>asin

Returns the arcsine of a number. The result is within the range of -Pi/2 to Pi/2. `asin` is the inverse of the `sin` function. The returned angle is measured in radians (not degrees).

```
dim d as double
d = asin(0.5)
```
```
dim d as double
d = asin(0.5) * 180.0 / pi
' the arc sine of 0.5 is 30 degrees
```

# <a name="atan"></a>atan

Returns the arctangent of the ratio *y*/*x*, where *y* is the vertical coordinate and *x* the horizontal coordinate.  The result is withing the range of -Pi to Pi. `atan` is the inverse of the `tan` function. The returned angle is measured in radians (not degrees).

#### Syntax

```
angle = atan(y, x) 
```

| Name       | Description |
| ---------- | ----------- |
| *y* | Value representing the proportion of the y-coordinate. |
| *x* | Value representing the proportion of the x-coordinate. |

```
dim d as double
d = atan(0.5, sqr(0.75))
' Output: 3.1415926535897931
```

# <a name="atn"></a>atn

Returns the arctangent of a number. The result is within the range of -Pi/2..Pi/2. `atn` is the inverse of the `tan` function. The returned angle is measured in radians (not degrees).

#### Syntax

```
angle = atn(number) 
```
```
dim d as double
d = atn(1) * 4
' Output: 3.1415926535897931
```

# <a name="ceil"></a>ceil

Rounds a float number upward, returning the smallest integral value that is not less than the float number.

#### Syntax

```
IntegerValue = ceil(FloatValue) 
```

**Output**:

```
value   round   floor   ceil    trunc
-----   -----   -----   ----    -----
 2.3     2.0     2.0     3.0     2.0
 3.8     4.0     3.0     4.0     3.0
 5.5     6.0     5.0     6.0     5.0
-2.3    -2.0    -3.0    -2.0    -2.0
-3.8    -4.0    -4.0    -3.0    -3.0
-5.5    -6.0    -6.0    -5.0    -5.0
```

# <a name="cos"></a>cos

Returns the cosine of an angle in radians. The result is within the range of -1.0 to 1.0.

```
dim d as double
d = cos(pi / 3)
```
```
dim d as double
d = cos (60.0 * PI / 180.0)
```

# <a name="deg"></a>deg

Converts radians to degrees.

```
dim d as double
d = deg(pi)
' Output: 180
```

# <a name="floor"></a>floor

Rounds a float number downward, returning the largest integral value that is not greater than the float number.

#### Syntax

```
IntegerValue = float(FloatValue) 
```

**Output**:

```
value   round   floor   ceil    trunc
-----   -----   -----   ----    -----
 2.3     2.0     2.0     3.0     2.0
 3.8     4.0     3.0     4.0     3.0
 5.5     6.0     5.0     6.0     5.0
-2.3    -2.0    -3.0    -2.0    -2.0
-3.8    -4.0    -4.0    -3.0    -3.0
-5.5    -6.0    -6.0    -5.0    -5.0
```

# <a name="frac"></a>frac

Returns the fractional part of a number

```
dim d as double
d = frac(123.456)
' Output: 0.456
```

# <a name="hypot"></a>hypot

Returns the hypotenuse (longest side) of a right angle triangle given the other 2 sides.

```
dim d as double
d = hypot(3, 4)
```

# <a name="lin"></a>lin

Returns the logarthm of the first value to base e (2.71828182845904523536…).

```
dim d as double
d = log(10)
print d   ' Output: 2.30258092...
```

# <a name="log"></a>log

Returns the natural logarithm of a given number.

```
dim d as double
d = log(10)
```

# <a name="log2"></a>log2

Returns the binary (base-2) logarithm of a number.

```
dim d as double
d = log2(32)
```

# <a name="log10"></a>log10

Returns the common (base-10) logarithm of a number.

```
dim d as double
d = log10(100)
```

# <a name="logn"></a>logn

Returns the logarthm of the first value to the base of the second value.

```
dim d as double
d = logn(1000, 10)
```

# <a name="mod"></a>mod

Returns the remainder of first value divided by the second value.

```
dim d as double
d = mod(83.5, 10)
' Output: 3.5
```

# <a name="pi"></a>pi

Returns pi, the ratio of the circumference of a circle to its diameter.

```
print pi
' Output: 3.1415926535897931
```

# <a name="pow"></a>pow

Returns the value of the first value raised to the power of the exponent. It is equivalent to the ^ operator.

```
dim d as double
d = pow(3)
' Output: 8
```

# <a name="rad"></a>rad

Converts from degrees to radians.

```
dim d as double
d = rad(180)
' Output: 3.1415926535897931
```

# <a name="recip"></a>recip

Returns the reciprocal of a value (x = 1 / v).

```
dim d as double
d = recip(5 / 4)
' Output: 0.8
```

# <a name="round"></a>round

Returns the integral value that is nearest to the passed float number.

#### Syntax

```
IntegerValue = round(FloatValue) 
```

**Output**:

```
value   round   floor   ceil    trunc
-----   -----   -----   ----    -----
 2.3     2.0     2.0     3.0     2.0
 3.8     4.0     3.0     4.0     3.0
 5.5     6.0     5.0     6.0     5.0
-2.3    -2.0    -3.0    -2.0    -2.0
-3.8    -4.0    -4.0    -3.0    -3.0
-5.5    -6.0    -6.0    -5.0    -5.0
```

# <a name="sgn"></a>sgn

Returns the sign part of a number.

* If number is greater than zero, it returns 1.
* If number is equal to zero, it returns 0.
* If number is less than zero, it returns -1.

```
result = sgn(-42)
```

# <a name="sin"></a>sin

Returns the sine of an angle given its value in radians.

```
dim d as double
d = sin(pi / 6)
' Output: 0.5
```

# <a name="sqr"></a>sqr / sqrt

Returns the square root of a number.

```
dim d as double
d = sqr(9)
' Output: 3
```

# <a name="tan"></a>tan

Returns the tangent of a value given in radians.

```
result = tan(radians)
```

# <a name="trunc"></a>trunc

Rounds a float number towards zero, returning the nearest integral value that is not larger in magnitude than the float number.

#### Syntax

```
IntegerValue = trunc(FloatValue) 
```

**Output**:

```
value   round   floor   ceil    trunc
-----   -----   -----   ----    -----
 2.3     2.0     2.0     3.0     2.0
 3.8     4.0     3.0     4.0     3.0
 5.5     6.0     5.0     6.0     5.0
-2.3    -2.0    -3.0    -2.0    -2.0
-3.8    -4.0    -4.0    -3.0    -3.0
-5.5    -6.0    -6.0    -5.0    -5.0
```

# <a name="hibyte"></a>hibyte

Returns the high-order byte an integer value (bits 8..15).

```
result = hibyte ( expression )
```

# <a name="lobyte"></a>lobyte

Returns the low-order byte an integer value (bits 0..7).

```
result = lobyte ( expression )
```

# <a name="hiword"></a>hiword

Returns the high-order word an integer value (bits 16..31).

```
result = hiword ( expression )
```

# <a name="loword"></a>loword

Returns the low-order word an integer value (bits 0..15).

```
result = loword ( expression )
```

# <a name="copy"></a>copy / copyn

Copies the values of *NumBytes* from the location pointed to by *SourceAddress* directly to the memory block pointed to by *DestinationAddress*. `copy` and `copyn` are the same.

#### Syntax

```
sub copy (DestinationAddress, SourceAddress, NumBytes)
```

The underlying type of the objects pointed to by both the source and destination pointers are irrelevant for this procedure; the result is a binary copy of the data. This proceudre does not check for any terminating null character in source: it always copies exactly num bytes.

To avoid overflows, the size of the memory blocks pointed to by both the *DestinationAddress* and *SourceAddress* parameters, shall be at least *NumBytes*, and should not overlap.

```
copy &dest, &src, n
copyn &dest, &src, n
```

# <a name="copy0"></a>copy0

Copies a null terminated string to another location.

```
sub copy0 (DestinationAddress, SourceAddress)
```

```
copy0 &dest, &src
```

# <a name="copy00"></a>copy00

Copies a null terminated string of wide (2 bytes) characters to another location.

```
sub copy00 (DestinationAddress, SourceAddress)
```

```
copy00 &dest, &src
```

# <a name="freememory"></a>freememory

Frees a previously allocated memory block.

```
dim pmem as sys
pmem = getmemory(8000)
'...
freememory pmem
```

# <a name="getmemory"></a>getmemory

Allocates a block of memory and returns its base address.

```
dim pmem as sys
pmem = getmemory(8000)
'...
freememory pmem
```
