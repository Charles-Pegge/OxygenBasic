# Variables, Arrays and User Defined Types

* `Variables` represent numeric or string values. The value of a variable can change during program execution. 
* `Constants` are numbers or strings which cannot be changed after they are defined.
* `Equates` are constants prefixed by the symbols `$` (string equates) or `%` (numeric equates).
* `Enums` are groups of logically related numeric equates.
* `User defined types` (UDTs) are custom data types containing one or more data fields.
* `Unions` are similar to a user defined types, except that the elements of a union occupy the same space in memory.
* `Arrays` are groups of data sharing the same variable name. The individual values that make up an array are called elements.


#### Variable Scope

* `Global` variables are accessible from anywhere in your program. They are initialized when your program starts and are destroyed when the program ends.
* `Local` variables are only accessible within a single procedure or method. They are automatically created and initialized each time you enter the procedure. They are automatically destroyed when you exit the procedure. This is the default variable scope unless you declare otherwise.
* `Static` variables are only accessible within a single proceudre or method. They are initialized when your program starts, but retain their value regardless of how many times the procedure is entered and exited. They are destroyed only when the program ends.

### Variables

| Name       | Description |
| ---------- | ----------- |
| [dim](#dim) | Declares variables, arrays, objects and user defined types. |
| [redim](#redim) | Creates or resizes a dynamic array, preserving contents within range.  |
| [as](#as) | Part of a declaration which specifies a data type. |
| [at](#dim) | Part of a declaration which specifies an absolute address. |
| [byref](#byref) | Declares a reference (by name) to a variable. |
| [let](#let) | Similar to **dim**, but the type is inferred from the assigned value. |
| [var](#var) | Defines a set of variables. |
| [const](#const) | Constant. Non-modifiable variable declaration. |
| [$](#equate1) | Defines a string equate (which can be used as constant). |
| [%](#equate2) | Defines a numeric equate (which can be used as constant). |
| [enum](#enum) | Declares an enumerated type. |
| [type](#type) | Define a compound variable type. |
| [union](#union) | Define a union. |

### Modifiers

| Name       | Description |
| ---------- | ----------- |
| [global](#global) | Declares global (shared) variables. |
| [local](#local) | Declares local variables inside a poceudre. |
| [static](#static) | Declares static variables inside a procedure. |

### Attributes

| Name       | Description |
| ---------- | ----------- |
| [len](#len) | Returns the length of a string in charaters. |
| [offsetof](#offsetof) | Returns the offset of variable from index register. |
| [recordof](#recordof) | Returns the record of a compound (UDT) variable. |
| [sizeof](#sizeof) | Returns the length of variable element (in bytes). |
| [spanof](#spanof) | Returns the span of array variable dimension.  |
| [typecodeof](#typecodeof) | Returns the type code number of variables and literals. |
| [typeof](#typeof) | Returns the name of the variable type. |

### Blocks and Scopes

| Name       | Description |
| ---------- | ----------- |
| [block](#block) | Creates a block of code. |
| [namespace](#namespace) | Declares a namespace block. |
| [rem](#rem) | Comments till end of line. |
| [//](#rem2)| Comments till end of line. |
| [\/\*](#rem3) | Comments till end of block. |
| [\*/](#rem3) | Terminates comment block. |
| [scope](#scope) | Creates a block where variables and functions may be locally defined. |
| [skip](#skip) | Prevents code within the block from being executed. |
| [::](#scopeop) | Scope resolution operator. |

# <a name="dim"></a>dim

Declares variables, arrays, objects and user defined types.

`dim` can specify an absolute address using the `at` address syntax, creating an overlay that allows to access the contents pointed by the absolute address to a different data type. See the "Overlays" examples below.

#### Syntax

Post define type

```
dim x as long
dim i, j, k as long
```

Pre define type

```
dim as long x
dim as long i, j, k
```

Mixed types

```
dim as log i, j, k, as string s, t
```

Multiline

```
dim as long i, j, k,
   as string s,t
```

```
dim as long,
   i,
   j,
   k
```

Initial values

```
dim as long,
   i = 1,
   j = 2,
   k = 42
```

Spread lines and comments

```
dim as long,
   i = 1,  ' these can be spread over many lines
   ' ---------
   j = 2,  ' with intervening comments
   ' ---------
   k = 42  '
```

Multiple assignments

```
dim as long a(10) => (2, 4, 6, 8, 10, 12, 42, 99)
```

Syntax variations

```
dim long a(10) => (2,4,6,8,10,12,42,99)  
dim long a[10] => (2,4,6,8,10,12,42,99)  
long a[10] => (2,4,6,8,10,12,42,99)  
long a[10] <= (2,4,6,8,10,12,42,99)  
long a[10] = {2,4,6,8,10,12,42,99}
long a[] = {2,4,6,8,10,12,42,99}
long a = {2,4,6,8,10,12,42,99}
```

Pointered variable

```
dim a as string = "ABCDEFGHI"
dim as string a =  "ABCDEFGHI"
dim byte b at strptr(a)
dim byte byref b : @b = strptr(a)
byte b at strptr(a)
byteE *b = strptr(a)
print b[7]   ' 71 G
```

Using dynamic memory

```
dim float f at getmemory 1024 * 4
f => (1.5, 2.5, 3.5)
print f[2]
freememory @f   ' release allocated memory
```

Global, static, local

```
global int g = 1
function f (p AS int) AS int
   static int s = 0
   local int l = 100
   s += 10
   return p + l + s + g
end function
print f(1000)   ' 1111
print f(1000)   ' 1121
```

Limiting scope

```
dim long a = 16
scope
   dim long a = 1
   print a   ' 1
end scope
print a   ' 16
```

Static arrays

```
dim as long a(10 )= {2,4,6,8,10,12}
a(10) = a(1) + a(4)
print a(10)
```

Dynamic arrays

```
dim as long a at getmemory(10 * sizeof(long))
a = {2,4,6,8,10,12}
...
freememory @a
```

```
dim as long a(10) = {2,4,6,8,10,12}
```

Overlays

```
dim as string s = "ABCDEFGHIJ"
dim as byte b at strptr(s)
print str(b[3]) ":  " chr(b[3])   ' 67 - "C"

Which is equivalent to:

dim as string s = "ABCDEFGHIJ"
dim as byte b ptr
@b = strptr(s)
print str(b[3]) ":  " chr(b[3])

Alternate way:

dim rg(1 to 10) as byte at strptr(s)
print rg(3)   ' 67 - "c"
```

```
float f = 123.45
DIM i as int at @f
print hex(i, 8)

Which is equivalent to cast the float value f to the integer i.

float f = 123.45
dim i as int = (int)f
print hex(i, 8)
```

There are 2 forms of `at`

Direct coupling to pointer *p*
```
mytype v at p
```
if *p* changes then so does *@v*

The address is the value of the expression *(p)*
```
mytype v at (p)
```
*@v* is independent of *p* thereafter

Multidimensional arrays

```
macro a(x,y) av(y * 1024 + x)
dim int av[1024 * 1024]
a(100,200) = 42
print a(100,200)   ' 42
```

Index base

```
dim int a[100] = {10,20,30,40}
indexbase 1    ' default: first element is indexed as 1
print a[2]   ' 20
indexbase 0
print a[2]   ' 30
```

Pseudo arrays

```
dim av[100]

function a(int i,v)   ' setter
   i *= 2
   av[i]=v
end function
  
function a(int i) as int   ' getter
   i *= 2
   return av[i]
end function

a(7) = 42   ' this is interpreted as a(7,42)
print a(7)
```

# <a name="redim"></a>redim

Creates or resizes a dynamic array, preserving contents within range. Used to extend or reduce an array size at runtime.

```
redim string s(20)
```

To flush an array's contents, redim it with 0 elements first. But avoid doing this with arrays of strings; the orphaned strings are not garbage-collected until the end of the program, and will accumulate on each iteration where the redim reduces the number of elements.


# <a name="as"></a>as

Part of a declaration which specifies a data type. `as` is used to declare the type of variables, fields or arguments.

```
dim x as long
dim as long x
```

# <a name="byref"></a>byref

Declares a reference (by name) to a variable. A reference is a way to access data located in memory like using a pointer that is implicitly dereferenced.

```
dim a as string = "ABCDEFGHI"
dim byte byref b
@b = strptr(a)
print b[7]   ' 71 G
```

```
' Alternate way:
dim a as string = "ABCDEFGHI"
byte *b = strptr(a)
print b[7]   ' 71 G
```

```
' Alternate way:
dim a as string = "ABCDEFGHI"
byte b at strptr(a)
print b[7]   ' 71 G
```

```
dim as word byref BYREF a = getmemory(1024)
' equivalent in C notation:
word * v = getmemory(1024)
' equivalent using 'at':
word v at getmemory(1024)
```

# <a name="let"></a>let

Similar to `dim` but the type is inferred from the assigned value.

```
let s = "This is a string"
print typeof(s)  ' Result: "string"
```

# <a name="var"></a>var

Defines a set of variables.

```
var string s, t, u(64), v  
```

`var` is normally only used internally. it accepts `*` for indirect variables and `at`for variable mapping. Arrays are also supported.


# <a name="const"></a>const

Non-modifiable variable declaration.

#### Syntax

```
const symbolname1 [as datatype] = value1 [, symbolname2 [as datatype] = value2, ...]
const [as datatype] symbolname1 = value1 [, symbolname2 = value2, ...]
```

```
const x = 10
const x = 10, y = 11, z = 12
const long x = 123, y = 234, z = 456
const as long x = 123, y = 234, z = 456
const string s = "Hello"
const s as string = "Hello"
const as string s = "Hello"
```

# <a name="equate1"></a>String equate ($)

Defines a string equate, which can be used as a constant.

```
$s = "Hello World"
$ s = "Hello World"
```

For embedded quotemarks use ` as the outer quotemark (ascii 96).

```
$s = `Hello "World"`
```

# <a name="equate2"></a>String equate (%)

Defines a numeric equate, which can be used as a constant.

```
%n = 12345
% n = 12345
%n = 12345.56
%= e  b * c ' precalcuate e value ' 6
% f 8
%% f 7  ' default value 7 (unless previously defined)
%sp " "
%cm ","
```

$ % prefixes and suffixes are ignored
  
```
print "" a cm b cm c cm d cm e cm f   '1, 2, 3, four, 6, 8
'print %a cm %b cm %c cm %d cm %e cm f
```

Arguments are represented by %1 .. %9
  
```
% display "value of %1: " %1
print display d
```

# <a name="emum"></a>enum

Declares an enumerated type (a set of equates twhich are logically related).

```
enum myenum
   option1   ' becomes 0
   option2   ' becomes 1
   option3   ' becomes 2
end enum
```

```
enum myenum
   option1 = 100   ' becomes 100
   option2         ' becomes 101
   option3         ' becomes 102
end enum
```

```
enum myenum
   option1 = 100   ' becomes 100
   option2 = 222   ' becomes 222
   option3         ' becomes 223
end enum
```

```
enum myenum
   option1, option2, option3
end enum
```

C syntax is supported for this construct.

```
enum myenum
{
   option1
   option2
   option3
}
```

```
enum myenum {option1, option2, option3}
```

Also `enum bit` assigns values 1,2,4,8,16.. instead of 0,1,2,3,4..

```
enum bit myenum
   option1
   option2
   option3
end enum
```

New definitions override older ones:

```
enum myenum
   option1 = 1
   option2
   option3
end enum

enum myenum2
   option1 = 10
end enum
```

In the above code, *option1* becomes 10. To trap duplicate definitions use `#unique on`. `#unique` may be switched on and off for any section of code.

Overriding definitions is always allowed within a new scope:

```
#unique on
enum x
   a = 1, b, c
end enum

scope
  enum y
     a = 10, b, c
  end enum
  print b   'output: 11
end scope
print b   ' output: 2
```

# <a name="type"></a>type

Defines a compound variable type.

```
type rgbacolor
  red   as byte
  green as byte
  blue  as byte
  alpha as byte
end type
```

Derived type

```
type color32
   r as byte
   g as byte
   b as byte
   a as byte
   =
   rgba AS long   ' Union
end type

type colortext
   txt as string
   c as color32
end type

dim t as colortext
  
t.txt = "Color code"
t.c.r = 8
t.c.b = 16
t.c.g = 32
t.c.a = 64
  
print t.txt & ": " & hex(t.c.rgba)
```
#### Syntax variations

```
type color32
   byte r
   byte g
   byte b
   byte a
   =
   long rgba  ' Union    
end type
```

```
type color32
   byte r, g, b, a
   =
   long rgba  ' Union    
end type 
```

```
type color32 byte r, g, b, a = long rgba
```

```
type colortext string txt, color32 c
```

```
struct color32 { 
   byte r,g,b,a
   =
   long rgba
}
```

```
typedef struct _color32 { 
   byte r,g,b,a
   =
   long rgba
} color32, *pcolor32
```

```
typedef struct _color32 {
   union { 
      struct {
        byte r,g,b,a
      }
      long rgba
  }  
} color32, *pcolor32
```

# <a name="union"></a>union

Allows different variables to occupy the same space.

```
union myunion
   b as byte
   w as short
   i as long
end union

dim v AS MyUnion
v.b = 42
print v.b
print v.w
print v.i

Result: v.b = 42 : v.w = 42 : v.i = 42
```

#### Syntax variation:

```
union MyUnion
{
  byte  b
  short w
  long  i
}
```

# <a name="global"></a>global

Declares global (shared) variables. `global` variables are accessible from anywhere in your program. They are initialized when your program starts and are destroyed when the program ends.

```
global n as long = 123
global as long n = 123
dim global as long n = 123
```

# <a name="local"></a>local

Declares local variables inside a poceudre. `local` variables are only accessible within a single procedure or method. They are automatically created and initialized each time you enter the procedure. They are automatically destroyed when you exit the procedure. This is the default variable scope unless you declare otherwise.

```
local long n = 123
local as long n = 123
local string s = "Test string"
local as string s = "Test string"
```

# <a name="static"></a>static

Declares static variables inside a poceudre. `static` variables are only accessible within a single proceudre or method. They are initialized when your program starts, but retain their value regardless of how many times the procedure is entered and exited. They are destroyed only when the program ends.

```
static long n = 123
static as long n = 123
static string s = "Test string"
static as string s = "Test string"
```

# <a name="block"></a>block

Creates a block of code. When a variable is (re)defined with `dim` within a block structure, this local working variable can be used from its (re)definition until the end of the block. During this time, any variables outside the scope that have the same name will be ignored, and will not be accessible by that name. Any statements in the `block` before the variable is redefined will use the variable as defined outside the block.

```
sys i = 4
block
   sys i = 8
   print "inner block i = " i
end block
print i
```

```
(
  dim int i = 2
  print i
)
```

```
block {
  dim int i = 2
  print i
}
```

Non executable blocks

```
skip {
  dim int i = 2
  print i
}
```

```
/*
  dim int i = 2
  print i
*/
```

Assembly code blocks

```
mov eax,0
mov ecx,5
block
 inc eax
 dec ecx
 jg repeat 'jump back to 'block'
end block
```

```
mov eax,0
mov ecx,5
(
 inc eax
 dec ecx
 jg repeat 'jump back to '('
)
```

```
mov eax,0
mov ecx,5
(
 dec ecx
 jl exit 'jump forward to ')'
 inc eax
 repeat 'jump back to '('
)
print eax
```

# <a name="rem"></a>rem

Comments till end of line.

```
rem this is a comment
```

# <a name="namespace"></a>namespace

Declares a namespace block. A namespace is a declarative region that provides a scope to the identifiers (the names of types, functions, variables, etc) inside it. Namespaces are used to organize code into logical groups and to prevent name collisions that can occur especially when your code base includes multiple libraries. All identifiers at namespace scope are visible to one another without qualification. Identifiers outside the namespace can access the members by using the fully qualified name for each identifier, for example *namespace_name::variable_name*.

#### Syntax
```
namespace identifier
   [statements]
end namespace
```

```
int i = 1

namespace aa
   int i = 10
   sub foo
      print "foo from namespace aa"
   end sub
end namespace

namespace bb
   int i = 20
   sub foo
      print "foo from namespace bb"
   end sub
end namespace

print i + aa::i + bb::i   ' output: 31

namespace bb
   print i   ' output: 20
end namespace

print bb::i   ' output: 20

aa::foo
bb::foo
```

```
namespace x
   type t
      int x
      int y
   end type
end namespace

dim tt as x::t
tt.x = 11
print tt.x
```

```
namespace x
  typedef struct _color32 {
    union { 
      struct {
        byte r,g,b,a
      }
      long rgba
    }  
  } color32, *pcolor32
end namespace

dim c32 as x::color32
c32.rgba = 0xFFFEFC
print c32.r
print c32.g
print c32.b
```

A namespace can be declared in multiple blocks in a single file, and in multiple files. The compiler joins the parts together during preprocessing and the resulting namespace contains all the members declared in all the parts.

```
namespace aa
   int i = 10
end namespace

namespace bb
   int i = 20
end namespace

namespace aa
   int x = 11
end namespace

print aa::i
print bb::i
print aa::x
```

# <a name="rem2"></a>rem (//)

Comments till end of line.

```
// this is a comment
```

# <a name="rem3"></a>rem (\/\* \*/)

Comments a block

```
/* this is a comment */
```

# <a name="scope"></a>scope

Creates a block where variables and functions may be locally defined. When a variable is (re)defined with `dim` within a scope structure, this local working variable can be used from its (re)definition until the end of the scope. During this time, any variables outside the scope that have the same name will be ignored, and will not be accessible by that name. Any statements in the `scope` block before the variable is redefined will use the variable as defined outside the scope.

```
sys i = 4
scope
   sys i = 8
   print "inner scope i = " i
end scope
print i
```

```
sys i = 4
scope {
   sys i = 8
   print "inner block i = " i
}
print i
```

# <a name="skip"></a>skip

Prevents code within the block from being executed.

```
skin {
  dim int i = 2
  print i
}
```

# <a name="scopeop"></a>Scope resolution operator (::)

The scope resolution operator `::` is used to identify and disambiguate identifiers used in different scopes. To access the global namespace use `global::identifier`. The identifier can be a variable or a procedure.

```
namespace aa
   int i = 10
   int x = 22
end namespace

namespace bb
   int i = 11
   int x = 33
end namespace

print aa::i   ' output: 10
print bb::i   ' output: 11
```

# <a name="len"></a>len

Returns the length of a string in charaters.

```
dim v as long = len("Hello")
' Output: 5
```

# <a name="offsetof"></a>offsetof

Returns the offset of variable from index register.

```
dim nbytes as long = offsetof(variable)
```

# <a name="recordof"></a>recordof

Returns the record of a compound (UDT) variable.

```
type vt long v, double d
dim AS vt v
r = recordof(v)
' Result:
r = "
v 0 4 1 A0 , long
d 4 4 1 A0 , double
"
```

# <a name="sizeof"></a>sizeof

Returns the length of variable element (in bytes). When used with variable-length strings, it will return the size of the string descriptor.

```
dim n as long
dim nBytes as long = sizeof(n)
' Result: 4
```

```
dim d as double
dim nBytes as long = sizeof(d)
' Result: 8
```

```
dim s as string
dim nBytes as long = sizeof(s)
' Result: 4
```

# <a name="spanof"></a>spanof

Returns the span of array variable dimension.

```
dim as long v(10)
dim n as long = spanof(v)
```

# <a name="typecodeof"></a>typecodeof

Returns the type code number of variables and literals. Used to obtain data for diagnostics or reflective programming.

```
dim n as long
print typecodeof(n)
' Output 4
```

```
print typecodeof("Hello")
' Output: 193
```

# <a name="typeof"></a>typeof

Returns the name of the variable type.

```
dim v as long
dim s as string = typeof(v)
' s = "long"
```
