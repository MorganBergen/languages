#  01 homework

**cse 340 - programming language concepts**

all submissions must be pdf and should be typed.  
exceptions can be made for drawing parse trees, which can be handwritten and scenned in the submitted document.  

##  01 problem

consider the following regular expression (we omit the dot operator)

$R_{0} = 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9$

$R_{1} = 0 \mid 1 \mid 2 \mid 3 \mid 4 \mid 5 \mid 6 \mid 7 \mid 8 \mid 9$

$R_{2} = {\left( 0 \mid 1 \right)}^{*} R_{0} \left( 0 \mid 1 \right)$

$R{3} = 00 \; {R_{0}}^* \left( 0 \mid 1\right)^{*}$

$R_{4} = {R_{3}}^{*} {R_{2}}^{*} \; 000$

assume that the longest prefix-matching rule is used.  assume that ties are broken in favor of the regular expression listed first in the list.

1.  gievn an example of input which `getToken()` return $R_{0}$
2.  give an example of input for which `getToken()` return $R_{1}$
3.  give an example of input for which `getToken()` return $R_{2}$
4.  give an example of input for which `getToken()` return $R_{3}$
5.  give an example of input for which `getToken()` return $R_{4}$
6.  if `getToken()` is called repeatedly on the following input, what is the sequence of tokens returned?

    `99001101678100010101030123457000010`

##  02 problem

explain your answers by showing the step-by-step table.  
consider the grammar

```
S → AB
S → aB | ε
S → bB | abA | A
```

1.  show that this grammar is ambiguous by constructing two different leftmost derivations for the string `abba_`
2.  show that this grammar is ambiguous by constructing two different parse treeses for the string `abba`

##  03 problem

compute `FIRST` and `FOLLOW` sets for the following grammar

```
S → aABc | CD
A → DC   | BE | ε
B → aCB  | AF 
C → cC   | ε
D → CDb  | ε
E → eFc  
F → Fg   | ε
```

**show your work.  ans answer by itself does not count**
