#  01 homework

######  cse 340 - programming language concepts

######  01 problem

<small>

consider the following regular expression (we omit the dot operator)

$R_{0} = 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9$

$R_{1} = 0 \mid 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9$

$R_{2} = {\left( 0 \mid 1 \right)}^{*} R_{0} \left( 0 \mid 1 \right)$

$R_{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*}$

$R_{4} = {R_{3}}^{*} {R_{2}}^{*} \; 000$

assume that the longest prefix-matching rule is used.  

assume that ties are broken in favor of the regular expression listed first in the list.

1.  give an example of input which `getToken()` return $R_{0}$
2.  give an example of input for which `getToken()` return $R_{1}$
3.  give an example of input for which `getToken()` return $R_{2}$
4.  give an example of input for which `getToken()` return $R_{3}$
5.  give an example of input for which `getToken()` return $R_{4}$
6.  if `getToken()` is called repeatedly on the following input, what is the sequence of tokens returned?

    `99001101678100010101030123457000010`

-----

1.  $R_{0} = \{ (1), (2), (3), (4), (5), (6), (7), (8), \text{or } (9) \}$
2.  $R_{1} = \{ ( 0 \mid 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9 ) \}$
3.  $R_{2} = {\left( 0 \mid 1 \right)}^{*} R_{0} \left( 0 \mid 1 \right)$


$R_{0} = \{ ( 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9 ) \}$

$R_{0} = \left( 1 \right)$  
$R_{0} = \left( 2 \right)$  
$R_{0} = \left( 3 \right)$  
$R_{0} = \left( 4 \right)$  
$R_{0} = \left( 5 \right)$  
$R_{0} = \left( 6 \right)$  
$R_{0} = \left( 7 \right)$  
$R_{0} = \left( 8 \right)$  
$R_{0} = \left( 9 \right)$  

the set of strings that match $R_{0}$ is the set of all strings that start with a digit from 1 to 9, of length 1

therefore there are possible 9 strings that match $R_{0}$

$R_{1} = \{ ( 0 \mid 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9 ) \}$

$R_{1} = \left( 0 \right)$  
$R_{1} = \left( 1 \right)$  
$R_{1} = \left( 2 \right)$  
$R_{1} = \left( 3 \right)$  
$R_{1} = \left( 4 \right)$  
$R_{1} = \left( 5 \right)$  
$R_{1} = \left( 6 \right)$  
$R_{1} = \left( 7 \right)$  
$R_{1} = \left( 8 \right)$  
$R_{1} = \left( 9 \right)$  

the set of strings that match $R_{1}$ is the set of all strings that start with a digit from 0 to 9, of length 1

therefore there are possible 10 strings that match $R_{1}$

$R_{2} = {\left(\left( 0 \mid 1 \right)\right)}^{*} R_{0} \left( 0 \mid 1 \right)$

$R_{2} = \{ {\left( 0 \mid 1 \right)}^{*} \} \; \cdot \{ R_{0} \} \cdot \; \{ \left( 0 \mid 1 \right) \}$

$\left( 0 \mid 1 \right)^{*} = \empty, 0, 1, 00, 01, 10, 11, 000, 001, 001, 010, 011, \text{ or } ...$ 

$\cdot$ (concatenation)

$*$ kleene star operator, means zero or more occurrences of the preceding expression

$R_{0} = 1, 2, 3, 4, 5, 6, 7, 8, \text{ or } 9$

$\cdot$ (concatenation)

$(0 \mid 1) = 0 \text{ or } 1$

possible strings from $R_{2}$

$R_{2} = \{ {\left( 0 \mid 1 \right)}^{*} \} \; \cdot \{ R_{0} \} \cdot \; \{ \left( 0 \mid 1 \right) \}$

$R_{2} =  \{ (\empty) \} \cdot \{(1)\} \cdot \{(0)\} = \empty \cdot 1 \cdot 0 = 10$

$R_{2} =  \{ (\empty) \} \cdot \{(1)\} \cdot \{(1)\} = \empty \cdot 1 \cdot 1 = 11$

$R_{2} =  \{ (\empty) \} \cdot \{(2)\} \cdot \{(0)\} = \empty \cdot 2 \cdot 0 = 20$

$R_{2} =  \{ (\empty) \} \cdot \{(2)\} \cdot \{(1)\} = \empty \cdot 2 \cdot 1 = 21$

$R_{2} =  \{ (\empty) \} \cdot \{(3)\} \cdot \{(0)\} = \empty \cdot 3 \cdot 0 = 30$

$R_{2} =  \{ (\empty) \} \cdot \{(3)\} \cdot \{(1)\} = \empty \cdot 3 \cdot 1 = 31$

$R_{2} =  \{ (0) \} \cdot \{(1)\} \cdot \{(0)\} = 0 \cdot 1 \cdot 0 = 010$

$R_{2} =  \{ (0) \} \cdot \{(1)\} \cdot \{(1)\} = 0 \cdot 1 \cdot 1 = 011$

$R_{2} =  \{ (0) \} \cdot \{(2)\} \cdot \{(0)\} = 0 \cdot 2 \cdot 0 = 020$

$R_{2} =  \{ (0) \} \cdot \{(2)\} \cdot \{(1)\} = 0 \cdot 2 \cdot 1 = 021$

$R_{2} =  \{ (0) \} \cdot \{(3)\} \cdot \{(0)\} = 0 \cdot 3 \cdot 0 = 030$

$R_{2} =  \{ (0) \} \cdot \{(3)\} \cdot \{(1)\} = 0 \cdot 3 \cdot 1 = 031$

$R_{2} =  \{ (1) \} \cdot \{(1)\} \cdot \{(0)\} = 1 \cdot 1 \cdot 0 = 110$

$R_{2} =  \{ (1) \} \cdot \{(1)\} \cdot \{(1)\} = 1 \cdot 1 \cdot 1 = 111$

$R_{2} =  \{ (1) \} \cdot \{(2)\} \cdot \{(0)\} = 1 \cdot 2 \cdot 0 = 120$

$R_{2} =  \{ (1) \} \cdot \{(2)\} \cdot \{(1)\} = 1 \cdot 2 \cdot 1 = 121$

$R_{2} =  \{ (1) \} \cdot \{(3)\} \cdot \{(0)\} = 1 \cdot 3 \cdot 0 = 130$

$R_{2} =  \{ (1) \} \cdot \{(3)\} \cdot \{(1)\} = 1 \cdot 3 \cdot 1 = 131$

$R_{2} =  \{ (00) \} \cdot \{(1)\} \cdot \{(0)\} = 00 \cdot 1 \cdot 0 = 0010$

$R_{2} =  \{ (00) \} \cdot \{(1)\} \cdot \{(1)\} = 00 \cdot 1 \cdot 1 = 0011$

$R_{2} =  \{ (00) \} \cdot \{(2)\} \cdot \{(0)\} = 00 \cdot 2 \cdot 0 = 0020$

$R_{2} =  \{ (00) \} \cdot \{(2)\} \cdot \{(1)\} = 00 \cdot 2 \cdot 1 = 0021$

$R_{2} =  \{ (00) \} \cdot \{(3)\} \cdot \{(0)\} = 00 \cdot 3 \cdot 0 = 0030$

$R_{2} =  \{ (00) \} \cdot \{(3)\} \cdot \{(1)\} = 00 \cdot 3 \cdot 1 = 0031$

therefore there are an infinite number of strings that match $R_{2}$

$R_{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*}$

$00 = 00$ 

$R_{0}^{*} = \{ ( 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9 )^{*} \} = \{ 1 \}, \{ 2 \}, \{12\}, \{222\}, \{17294\}, \cdots$

$\left( 0 \mid 1\right)^{*} = \{0\}, \{1\}, \{00\}, \{01\}, \{10\}, \{11\}, \{000\}, \{010\}, \cdots$

$R_{0}^{*}$ is the set of all strings that can be formed by zero, one, or more occurrences of any single digit from 1 to 9, concatenated together.

$R_{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*} = 00 \cdot 1 \cdot 0$

$R_{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*} = 00 \cdot 1 \cdot 1$

$R_{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*} = 00 \cdot 1 \cdot 0$

$R_{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*} = 00 \cdot 1 \cdot 11$

$R_{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*} = 00 \cdot 1 \cdot 00$

$R_{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*} = 00 \cdot 2 \cdot 001$

$R_{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*} = 00 \cdot 72391 \cdot 0001011$

therefore there are an infinite number of strings that match $R_{3}$

$R_{4} = {R_{3}}^{*} {R_{2}}^{*} \; 000$

$R_{4} = \{ {R_{3}}^{*} \} \cdot \{ {R_{2}}^{*} \} \cdot \{ 000 \}$

$R_{4} = (\; 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*} \;)^{*}  \cdot (\{ {\left( 0 \mid 1 \right)}^{*} \} \; \cdot \{ R_{0} \} \cdot \; \{ \left( 0 \mid 1 \right) \}) \cdot 000$


</small>


-------------

$R_{0} = \{ ( 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9 ) \}$  

$R_{1} = \{ ( 0 \mid 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9 ) \}$  

$R_{2} = \{ ( ( 0 \mid 1 )^{*} ) \cdot ( 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9 ) \cdot ( 0 \mid 1 ) \}$  

$R_{3} = \{ 00 \cdot ( 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9 )^{*} \cdot ( 0 \mid 1 )^{*} \}$  

$R_{4} = \{ ( 00 \cdot ( 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9 )^{*} \cdot ( 0 \mid 1 )^{*} )^{*} \cdot 000 \}$  

######  about

<small>
this problem is about lexical analysis, which is the first phase of a compiler.  the goal of a lexical analyzer (often called "lexer" or "scanner") is to read the input source code (a string of characters) and group them into a sequence of tokens.  tokens are meaningful units of a programming language, like keywords, identifiers, numbers, operators. etc.  regular expressions are a powerful way to define the patterns for these tokens.
</small>

######  1.  understanding regular expressions

<small>

a regular expression defines a language, (the set of all strings that the regular expression describes).

$R_{0}, R_{1}, R_{2}, R_{3}, R_{4}$

$\mid$ means `OR`  

$R_{0} = 1 \mid 2 \mid ... \mid 9$ means that $R_{0}$ can be any single digit from 1 to 9.

$\cdot$ means `concatenation`

$R_{0} \cdot R_{1}$ means that the string must start with a digit from 1 to 9, followed by a digit from 0 to 9.

$^{*}$ means `zero or more occurrences` of the preceding expression.  

for example, $R_{0}^{*}$ means zero or more occurrences of any non-zero digit

$(0 \mid 1)^{*}$ means zero or more occurrences of either $0$ or $1$

$($ $)$ means `grouping`

$R_{0} \left( 0 \mid 1 \right)$ means that the string must start with a digit from 1 to 9, followed by either $0$ or $1$

</small>

######  2.  understanding the `getToken()` function

<small>

`getToken()` function

image this is a function that looks at the beginning of the current input string.  
it tries to find the longest possible prefix (substring from the beginning) of the input that matches one of the defined regular expression $R_{0}$ through $R_{4}$.

</small>

######  3.  understanding the longest prefix matching rule 

<small>

longest prefix matching rule

this is crucial.  if multiple regular expressions could match a prefix of the input, the one that matches the longest string of characters is chosen.

</small>

######  4.  tie-breaking rule

<small>

if after applying the longest prefix matching rule, there's still a tie (i.e. multiple regular expressions match the same longest prefix), the tie is broken by choosing the regular expression that is listed first in the definition.  in your first case, the order is $R_{0}, R_{1}, R_{2}, R_{3}, R_{4}$.

</small>

######  5.  repeated calls to `getToken()` when `getToken()` is called repeatedly, it means...

<small>
the first call finds a token at the beginning of the input

the matched portion of the input is "consumed", (removed)

the next call to `getToken()` looks at the remaining input string to find the next token, and so on until the entire input is processed.
</small>


-------------

#  example 1

simpler set of regular expressions and an input string to demonstrate the process.

assume we have the following regular expression, in this order of priority for tie breaking

$T_{A} = \text{id}$

$T_{B} = \text{int}$

$T_{C} = \text{id\text{(int)}}^{*}$

$\text{id} = a \mid b \mid c$

$\text{int} = 0 \mid 1 \mid 9$

an $\text{id}$ followed by zero or more $\text{int}$

$T_{A}$ is the first token in the list, so it has the highest priority.

$T_{B}$ is the second token in the list, so it has the second highest priority.

$T_{C}$ is the third token in the list, so it has the third highest priority.

----

$T_{A} = \text{id} = \{ a \mid b \mid c \}$

$T_{B} = \text{int} = \{ 0 \mid 1 \mid 9 \}$

$T_{C} = \text{id\text{(int)}}^{*} = \left(a \mid b \mid c \right) \left( \left( 0 \mid 1 \mid 9 \right) \right)^{*}$


example of all strings matching $T_{A}$ are `a`, `b`, or `c` (no other strings match $T_{A}$)

example of all strings matching $T_{B}$ are `0`, `1`, or `9` (no other strings match $T_{B}$)

example of all strings matching $T_{C}$ are `a`, `a0`, `b19`, `c0190`, etc.

rules

1.  longest prefix matching
2.  tie breaking $T_{A}$ first, then $T_{B}$, then $T_{C}$

part 1 given an example of input for which `getToken()` returns a specific token

1.  give an example of input for which `getToken()` returns $T_{A}$
2.  give an example of input for which `getToken()` returns $T_{B}$
3.  give an example of input for which `getToken()` returns $T_{C}$


question 1

give an example of input for which `getToken()` returns $T_{A}$

thinking:  we need an input where $T_{A}$ is the longest match, or if there's a tie in length, $T_{A}$ wins by priority

consider input `a`

$T_{A}$ matches `a` length 1

$T_{B}$ does not match

$T_{C}$ matches `a` (the `(int)*` part matches zero occurrences of `int`). length 1

both $T_{A}$ and $T_{C}$ match `a` with length , this is a tie in length

by the tie breaking rule $T_{A}$ listen before $T_{C}$, $T_{A}$ is chosen

answer: `a` or `b` or `c`

question 2

give an example of input for whcih `getToken()` returns $T_{B}$

we need an input where $T_{B}$ is the longest match

consider input `1`

$T_{A}$ does not match

$T_{B}$ matches `1` of length 1

$T_{C}$ does not match, it must start with an $\text{id}$ followed by zero or more $\text{int}$

answer `0`, `1`, or `9`

question 3 

give an input for which `getToken()` returns $T_{C}$

consider input `a0`

$T_{A}$ matches `a` of length 1

$T_{B}$ does not match (starts with `a`)

$T_{C}$ matches `a0`, $\text{id} =$ `a`, $\text{int} =$ `0`, length 2

longest match is `a0` by $T_{C}$

answer `a0`, `b1`, `c90`, `a019`, etc.

what about `a`?  we saw this gives $T_{A}$ due to tie breaking, for $T_{C}$ to win, it generally needs to match a longer prefix than $T_{A}$ or $T_{B}$ cannot match, or match the same length but be the only one, or win a tie break if other same length matches are lower prioritt (which isnt the case here since $T_{A}$ is higher priority for single 'id' characters)

part 2  if `getToken()` is called repeatedly on an input, what is the sequence of tokens returned?

input string `c90b1a`

step by step tokenization

call 1:

current input `c90b1a`

check $T_{A}$ `(a | b | c)` 

matches `c`. length 1

check $T_{B}$ `(0 | 1 | 9)` 

does not match `c`. length 0

check $T_{C}$ `(a | b | c)((0 | 1 | 9))*` 

matches `c`, `id = c`, `(int)* = null`. length 1

matches `c9` `id = c`, `int = 9`. length 2

matches `c90` `id = c`, `int = 90`. length 3

longest prefix match $T_{A}$ matches `c` of length 1

$T_{C}$ matches `c90` of length 3

token returned $T_{C}$

input consumed `c90`

remaining input `b1a`

call 2

current input `b1a`

check $T_{A}$ matches `b` of length 1

check $T_{B}$ does not match `b`

check $T_{C}$ `(a | b | c)((0 | 1 | 9))*`

$T_{C}$ matches `b`, `id = b`, `(int)* = null`, length 1

$T_{C}$ matches `b1` `id = b`, `int = 1`, length 2

longest prefix match 

$T_{A}$ matched `b` length 1

$T_{C}$ matches `b1` `id = b`, `int = 1`, length 2

the longest match is `b1` by $T_{C}$

token returned $T_{C}$

input consumed `b1`

remaining input `a`

call 3

current input `a`

check $T_{A}$ matches `a` of length 1

check $T_{B}$ does not match `a`

check $T_{C}$ `(a | b | c)((0 | 1 | 9))*`

$T_{C}$ matches `a`, `id = a`, `(int)* = null`, length 1

longest prefix match 

$T_{A}$ matched `a` length 1

$T_{C}$ matches `a`, `id = a`, `(int)* = null`, length 1

this is a tie in length both match `a`

tie breaking rule $T_{A}$ is listed before $T_{C}$, so $T_{A}$ wins

token returned $T_{A}$

input consumed `a`

remaining input `null`

final sequence of tokens returned $T_{C}, T_{C}, T_{A}$



