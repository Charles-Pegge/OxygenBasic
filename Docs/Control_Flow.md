# Control Flow

Statements that direct the flow of program execution.

### Transferring Statements

Statements that transfer control to another part of a program.

| Name       | Description |
| ---------- | ----------- |
| [goto](#goto) | Jumps unconditionally to a specified label in the code. |
| [gosub](#gosub) | Calls a labelled subroutine. |
| [ret](#ret) | Returns from a **gosub**. |
| [return](#return) | Returns from a procedure. |
| [exit sub](#exitsub) | Exits a procedure. |
| [exit function](#exitfunction) | Exits a function. |

### Branching Statements

Statements that execute one of a number of code branches.

| Name       | Description |
| ---------- | ----------- |
| [if](#if) | Starts a conditional block with a test. |
| [then](#then) | Starts the conditional block where the prior test is met. |
| [elseif](#elseif) | Makes an alternative test if the previous condition was not met. |
| [else](#else) | Starts the alternative block where none of the prior conditions are met. |
| [endif](#endif) | Ends the conditional block. |
| [select](#select) | Starts a case block. |
| [case](#select) | Specifies a case to match followed by actions to perform.  |
| [case else](#select) | Matches any case not already matched. |
| [end select](#select) | Ends the select block. |
| [endsel](#select) | Ends the select block. |
| [switch](#switch) | Starts a C style case block. |

### Looping Statements

Statements that execute code repeatedly.

| Name       | Description |
| ---------- | ----------- |
| [do](#do) | Starts a block for repetition (looping). |
| [end do](#enddo) | Ends a **do** repeating block. |
| [endddo](#enddo) | Ends a **do** repeating block. |
| [loop](#loop) | Ends a **do** repeating block. |
| [exit do](#exitdo) | Exits a **do** loop immediately. | |
| [continue do](#continuedo) | Goes back to the beginning of a **do** block. |
| [for](#for) | Starts an iteration block. |
| [to](#to) | Specifies the limit of an iteration. |
| [step](#step) | Specifies the increment of an iteration. |
| [next](#next) | Ends an iteration block. |
| [exit for](#exitfor) | Exits a **for** loop immediately. |
| [continue for](#continuefor) | Goes back to the beginning of a **for** block. |
| [while](#while) | Starts a block for conditional repetition. |
| [wend](#wend) | Ends a **while** block. |
| [end while](#endwhile) | Ends a **while** block. |
| [endwhile](#endwhile) | Ends a **while** block. |
| [exit ehile](#exitwhile) | Exits a **while** block immediately. |
| [continue while](#continuewhile) | Goes back to the beginning of a **while** block. |
| [repeat](#repeat) | Starts a block for conditional repetition. |
| [until](#until) | Continue executing a **repeat** loop until a condition is met. |
| [redo](#redo) | Starts a block for conditional repetition. |
| [break](#break) | Exits a **switch** block, a **do** block or a **while** block immediately. |
| [break when](#breakwhen) | Exits a **switch** block, a **do** block or a **while** block when a condition is met. |

# <a name="goto"></a>goto

Jumps unconditionally to a specified label or line number in the code. The label must be local to the **sub**, **function** or **method** where the `goto` statement is located. `goto` differs froom `gosub` in that after execution of a `goto`, the program retains no memory of where it was before it executed the jump. `goto` is considered bad programming practice as it can generate unreadable and untraceable code. It is better to use more modern structures such as `do..loop`, `for..next`, `sub`, and `function`.

```
if x = 1 then goto LExit
...
...
...

: LExit
```

```
10  rem Legacy
20  dim a as single, b as single, c as single, i as long
30  a = 1.0 : b = 1.0 : i = 0
40  c = a + b
60: i = i + 1
70: if i < 20 then a = b : b = c : goto 40
80:   
90: print "Approx Fibonacci number: " str(c / b)
```

# <a name="gosub"></a>gosub

Calls a labelled subroutine. Execution jumps to a subroutine marked by a line label. Always use `Ret` to exit a `gosub`, execution will continue on next statement after `gosub`. The line label where `gosub` jumps must be in the same main/function/sub block as `gosub`. All the variables in the subroutine are shared with the block and no arguments can be used. `gosub` is considered bad programming practice as it can generate unreadable and untraceable code. It is better to use `sub` or `function` instead.

```
subB Foo

  int a = 42
  int b

  gosub g
  print b
  return

g:
  b = a / 2
  ret

end sub
```

# <a name="ret"></a>ret

Terminates the execution of a subroutine and returns the control to the statement following the calling `gosub` statement. A `gosub` should always have a matching `ret` statement.

# <a name="return"></a>return

#### Syntax

```
return [expression]
```

Exits from a procedure. A `sub` cannot specify a return value. In a `sub`, it is roughly equivalent to `exit sub`. In a `function`, `return` must specify a return value. `return`*expression* is roughly equivalent to `function = expression : exit function`.

```
sub DisplayMessage (s as string)
   if s = "" then return
   print s
end sub
```

```
function Sum (byval x as long, byval z as long) as long
   return x + z
end function

print Sum(5, 3)
' Output: 8
```

# <a name="exitsub"></a>exit sub

Exits a procedure.

```
sub DisplayMessage (s as string)
   if s = "" then exit sub
   print s
end sub
```

# <a name="exitfunction"></a>exit function

Exits a function.

```
function Div (byval x as long, byval z as long) as long
   if z = 0 then exit function
   function = x + z
end function
```

# <a name="if"></a>if

Starts a conditional block with a test.

```
int a = 1, b = 2
if a < b then a = b
```

# <a name="then"></a>then

Starts the conditional block where the prior test is met.

```
int a = 1, b = 2
if a < b then a = b
```

Syntax variations:

```
if (a > b) {s = "A > B"} elseif (a = b) {s = "A = B"} else {s = "A < B"}
```
```
if a > b {s = "A > B"} elseif a = b {s = "A = B"} else {s = "A < B"}
```
```
if a > b {
   s = "A > B"
} elseif a = b {
   s = "A = B"
} else {
   s = "A < B"
}
```

# <a name="elseif"></a>elseif

Makes an alternative test if the previous condition was not met.

```
string s
int a = 1, b = 2
if a > b then
   s = "A > B"
elseif a = b then
   s = "A = B"
else
   s = "A < B"
end if
```

Syntax variations:

```
if (a > b) {s = "A > B"} elseif (a = b) {s = "A = B"} else {s = "A < B"}
```
```
if a > b {s = "A > B"} elseif a = b {s = "A = B"} else {s = "A < B"}
```
```
if a > b {
   s = "A > B"
} elseif a = b {
   s = "A = B"
} else {
   s = "A < B"
}
```

# <a name="else"></a>else

Starts the alternative block where none of the prior conditions are met.

```
string s
int a = 1, b = 2
if a > b then
   s = "A > B"
elseif a = b then
   s = "A = B"
else
   s = "A < B"
end if
```

Syntax variations:

```
if (a > b) {s = "A > B"} elseif (a = b) {s = "A = B"} else {s = "A < B"}
```
```
if a > b {s = "A > B"} elseif a = b {s = "A = B"} else {s = "A < B"}
```
```
if a > b {
   s = "A > B"
} elseif a = b {
   s = "A = B"
} else {
   s = "A < B"
}
```

# <a name="endif"></a>endif

Ends the conditional block.

```
string s
int a = 1, b = 2
if a > b then
   s = "A > B"
elseif a = b then
   s = "A = B"
else
   s = "A < B"
end if
```

# <a name="select"></a>select case / case else / end select / endsel

Starts a case block.

Compact form:

```
dim a as long, s as string
a = 3
select a   ' select case a
  case 1 : s = "A = 1"
  case 2 : s = "A = 2"
  case 3 : s = "A = 3"
  case else : s = "A > 3"
end select   ' or endsel
```

General form:

```
select a
  case 1
    s = "A = 1"
  case 2
    s = "A = 2"
  case 3
    s = "A = 3"
  case else
    s = "A > 3"
end select
```

Syntax variations:

```
select a {
  case 1
    s = "A = 1"
  case 2
    s = "A = 2"
  case 3
    s = "A = 3"
  case else
    s = "A > 3"
}
```

Extensions:

```
select a
  case 1
    s = "A = 1"
  case 2
    s = "A = 2"
  case 3
    s = "A = 3"
  case 4,5,6
    '
  case 7 to 9
    '
  case 10 to <20
    '
  case else
    s = "A > 3"
end select
```

```
select asc("qwerty", 1)
  case "a"toO "p"
    print "a to p"
  case "q" to "z"
    print "q to z"
  case else
    print "not lower case"
end select
```

```
select asc("qwerty", 1)
  case 'a' to 'p'   ' single quote marks
    print "a to p"
  case "q" to "z"
    print "q to z"
  case else
    print "not lower case"
end select
```

# <a name="switch"></a>switch

Starts a C style case block.

```
dim a as long, s as string
a = 3
switch a {
  case 1
    s = "A = 1"
    break
  case 2
    s = "A = 2"
    break
  case 3
    s = "A = 3"
    break
  case else
    s = "A > 3"
    break
}
```

# <a name="while"></a>while

Starts a block for conditional repetition.

```
dim a, b as long
a = 4
while b <= a
   b += 1
wend
```

# <a name="wend"></a>wend

Ends a `while` block.

```
dim a, b as long
a = 4
while b <= a
   b += 1
wend
```

# <a name="endwhile"></a>end while

Ends a `while` block.

```
dim a, b as long
a = 4
wgile b <= a
   b += 1
end while   ' or endwhile
```

# <a name="for"></a>for

Starts an iteration block.

#### Syntax

```
for iterator = startvalue to endvalue [ step stepvalue ]
   [ statement block ]
next
```

| Parameter  | Description |
| ---------- | ----------- |
| *iterator* | A variable identifier that is used to iterate from an initial value to an end value. |
| *startvalue* | An expression that denotes the starting value of the iterator. |
| *endvalue* | An expression used to compare with the value of the iterator. |
| *stepvalue* | An expression that is added to the iterator after every iteration. |

```
dim as long i, n
for i = 1 to 10
   n += 1
next
```

```
dim as long i, n
for i = 1 tO 10 step 2
   n += 1
next
```

```
dim as single i
for i = 3 to 0 step -0.5
   print i
next
```

```
dim as long i, b
dim s as string = "QWERTY"
for i = 1 to len(s)
   b += asc(s,i)
next
```

Syntax variations:

```
for i = 1 to len(s) step 1 {
   a = asc(s,i)
   b += a
}
```

```
for i = 1, len(s), 1 {
   a = asc(s,i)
   b += a
}
```

```
for (i = 1, i <= len(s), i++) {
   a = asc(s,i)
   b += a
}
```

```
#semicolon separator
for (i = 1; i <= len(s); i++) {
   a = asc(s,i)
   b += a
}
#semicolon comment
```

```
for (i = 1, i <= len(s), i++) {
   a = asc(s,i)
   b += a
}
```

# <a name="to"></a>to

Specifies the limit of an iteration.

```
dim as long i, n
for i = 1 to 10 step 2
   n += 1
next
```

# <a name="step"></a>step

Specifies the increment of an iteration.

```
dima s long i, n
for i = 1 to 10 step 2
   n += 1
next
```

```
dim as single i
for i = 3 to 0 step -0.5
   print i
next
```

# <a name="next"></a>next

Ends an iteration block.

```
dim as long i, n
for i = 1 to 10
   n += 1
next
```

# <a name="exitfor"></a>exit for

Exits a `for` loop immediately.

```
dim as long i, n
for i = 1 to 10
   n += 1
   if n = 5 then exit for
next
```

# <a name="do"></a>do

Starts a block for repetition (looping).

```
dim as long a, b
a = 4
do
   b += 1
   if b > a then exit do
end do   'or enddo
```

```
dim as long a, b
a = 4
do
   b += 1
   if b > a then exit do
loop
```

```
dim as long a, b
a = 4
do
   b += 1
loop while b < a
```

```
dim as long a, b
a = 4
do
   b += 1
loop until b >= a
```

```
dim as long a, b
a = 4
do
   b += 1
   if b >= a then break
loop
```

# <a name="enddo"></a>enddo

Ends a `do` repeating block.

```
dim as long a, b
a = 4
do
   b += 1
   if b > a then exit do
end do   'or enddo
```

# <a name="loop"></a>loop

Ends a `do` repeating block.

```
dim as long a, b
a = 4
do
   b += 1
   if b > a then exit do
loop
```

# <a name="exitdo"></a>exit do

Exits a `do` loop immediately.

```
dim as long a, b
a = 4
do
   b += 1
   if b > a then exit do
loop
```

# <a name="continuedo"></a>continue do

Goes back to the beginning of a `do` block.

```
dim as long a, b
a = 4
do
   b += 1
   if b < a then continue do
   if b >= a then exit do
loop
```

# <a name="continuefor"></a>continue for

Goes back to the beginning of a `for` block.

```
dim a, b, i as long
a = 4
for i = 1 to 10
   b += 1
   if b < a then continue for
   if b >= a then exit for
next
```

# <a name="continuewhile"></a>continue while

Goes back to the beginning of a `while` block.

```
dim a, b as long
a = 4
while b < a
   b += 1
   if b < a then continue while
wend
```
# <a name="repeat"></a>repeat

Starts a block for conditional repetition.

```
dim a, b as long
a = 4
do
   b += 1
   if b < a then repeat do
   IF b >= a then exit do
loop
```

```
dim a, b as long
a = 4
do
   b += 1
   repeat until b >= a
   if b >= a then exit do
loop
```

# <a name="until"></a>until

Continue executing a `repeat` loop until a condition is met.

```
dim a, b as long
a = 4
do
   b += 1
   repeat until b >= a
   if b >= a then exit do
loop
```

# <a name="redo"></a>redo

Starts a block for conditional repetition.

```
dim a, b as long
a = 4
do
   b += 1
   redo until b >= a
   if b >= a then exit do
loop
```

# <a name="break"></a>break

Exits a `switch`, `do` or `while` blocks.

```
dim a as long, s as string
a = 3
switch a {
  case 1
    s = "A = 1"
    break
  case 2
    s = "A = 2"
    break
  case 3
    s = "A = 3"
    break
  case else
    s = "A > 3"
    break
}
```

```
dim a, b as long
a = 4
do
   b += 1
   if b >= a then break
loop
```

```
dim a, b as long
a = 4
while b <= a
   b += 1
   if b = a then break
end while
```

# <a name="breakwhen"></a>break when

Exits a `switch`, `do` or `while` block when a condition is met.

```
dim a, b as long
a = 4
while b <= a
   b += 1
   break when b = a
end while
```

```
dim a, b as long
a = 4
do
   b += 1
   break when b = a
loop
```

```
dim a, b as long
a = 4
while b <= a
   b += 1
   break when b = a
wend
```
