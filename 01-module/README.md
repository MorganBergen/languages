#  01 regular expressions

[→ back](../README.md) 

[01.0 - overview](#010---overview)  
[01.1 - lexical analysis: language and syntax](#011---lexical-analysis-language-and-syntax)  
    
[01 principles of programming languages](#01-principles-of-programming-languages)

[02 lexical analysis](#02-lexical-analysis)

[01.2 - lexical analysis: regular expressions](#012---lexical-analysis-regular-expressions)  


[01.3 - lexical analysis: concatenation](#013---lexical-analysis-concatenation)  
[01.4 - lexical analysis: kleene star](#014---lexical-analysis-kleene-star)  
[01.5 - lexical analysis: regular expression examples](#015---lexical-analysis-regular-expression-examples)  
[01.6 - lexical analysis: longest matching prefix rule](#016---lexical-analysis-longest-matching-prefix-rule)  
[01.7 - practice quiz](#017---practice-quiz)

## 01.0 - overview  

**overview**

lexical analysis is the process of checking the syntac of a given programming language.  in lexical analysis, regular expressions are used as a way to represent the tokens of a programming language.  longest matching prefix rule says that if there are more than one match, the longest match should be returned and is a way of resolving ambiguity when there are multiple matches. 

**outcomes/objectives**

1.  explain what lexical analysis is
2.  describe what regular expressions are
3.  describe the language of a regular expression
4.  describe the concatenation of kleene star operator of regular expressions
5.  write regular expressions for a given token
6.  apply the longest matching prefix rule

**activities**

[lecture videos](./lecture-video.md)  
[powerpoint presentation](./powerpoint.md)    
[homework 1](./01-homework.md)  
[project 1](./01-project.md)  
[practice quiz](./practice-quiz.md)  

for project 1 you will work on a programming project implementing a lexer to generate toakens as discussed in this chapter.  refer to the project manual for complete details and the accompanying zip file for the starter code with some implementation.  refer to the project manual (instructions and implementation guide) for submission details.

your submission will be checked for plagiarism.  refer to the asu integrity policy.  collaboration with peers, getting coding help from outsite, and copying code from online resources such as github repositories, course hero, and chegg are not allowed.  you are not allowed to share the code or host it in a public repository.

**textbook readings**

**programming languages: principles and practice**

- [ ] chapter 1 - introduction - section 1.1 origins of programming languages
- [ ] chapter 1 - introduction - section 1.4 language definition  
- [ ] chapter 1 - introduction - section 1.5 language translation
- [ ] chapter 6 - syntax - section 6.1 lexical structure of programming languages  

**compiler construction: principles and practice**

- [ ] chapter 2 - scanning - section 2.2 regular expressions

## 01.1 - lexical analysis: language and syntax  

overview of programming languages.

what is a programming language, how does it work, and how does the computer know what to do?  view the following powerpoint to learn more.  

###  01 principles of programming languages

**contents**
1.  [what is a programming language](#what-is-a-programming-language)
2.  [how does the computer understand your instructions](#how-does-the-computer-understand-your-instructions)
3.  [how do they work](#how-do-they-work)
4.  [compiler](#compiler)
5.  [relocation](#relocation)
6.  [linker](#linker)
7.  [loader](#loader)
8.  [create a process](#create-a-process)
9.  [overview of program interpretation](#overview-of-program-interpretation)
10.  [what makes a program valid?](#what-makes-a-program-valid)

###  what is a programming language

-  a structured way to define computation
-  is it the only definition /  purpose?
    -  communicate an algorithm
    -  describe a process
    -  communicate a system to another person
    -  communicate instructions to a machine

###  how does the computer understand your instructions

the cpu understands assembly language

-  programs translate your intentions to the assembly language that the cpu understands
-  compilers
    -  translate programming language to executable binary
-  interpreters
    -  understand a programming language and perform the actual computation
-  transpilers
    -  translate a programming language to another programming language

###  how do they work

-  in this class we will study how these programs are able to translate a high level programming language into something the computer can understand

-  theory
    -  enables us to define what we can do and cannot do when defining a programming language
-  practice
    -  empowers us to develop domain specific languages, task specific compilers, static analysis, parsing...

###  compiler

compiler converts high level code into machine code (well not really)

relative references for functions define in your code

symbolic references for functions not defined in your code

<img src="./compiler.svg" alt="compiler" style="width: 400px;"/>

###  relocation

-  table of pointers to lines of code that need linking to different libraries
    -  the symbolic references
-  a symbol table is also created in this step, which has information about the symbols and what functions have to be loaded for a given symbol.
-  

###  linker

uses relation table to find lines of code to be replaced and then uses the symbol tables to find which functions have to be used.

<img src="./table.svg" alt="table" style="width: 400px;"/>

1.  create 1 output binary (merged), start at 0
2.  fix all local references with global relative addresses
3.  fix all symbolic refs

###  loader

<img src="./loader.svg" alt="loader" style="width: 400px;"/>

takes the output of linker and copies them to memory

<img src="./0-loader.svg" alt="0-loader" style="width: 400px;"/>

###  create a process

-  process control blocks `pcb`
   -  process id
   -  process counter = start address of code
   -  status register
-  put the `pcb` in the ready queue

###  overview of program interpretation

<img src="./interpretation.svg" alt="interpretation" style="width: 400px;"/>

###  what makes a program valid?

1.  **syntax**  what does it mean to look like a valid program?
2.  **semantics**  what does it mean for a program to be valid?
3.  **correctness**  is the program the correct one for the job?

-------------

lexical analysis

a programming language must have a clearly specified syntax.  lexical analysis is the process of checking the syntax of a given programming language.  refer to the lexical analysis powerpoint and watch the video below for more information.

###  02 lexical analysis

**contents**

1.  [language syntax](#language-syntax)
2.  [strings](#strings)
3.  [languages](#languages)
4.  [regular expressions](#regular-expressions)
5.  [$L \left( R_{1} \mid R_{2} \right) = L \left( R_{1} \right) \cup L \left( R_{2} \right)$](#l-r1-r2-l-r1-l-r2)
6.  [$L \left( R_{1} \cdot R_{2} \right) = L \left( R_{1} \right) \cdot L \left( R_{2} \right)$](#l-r1-r2-l-r1-l-r2)
7.  [operator precedence](#operator-precedence)
8.  [regular expressions](#regular-expressions-1)
9.  [kleene star](#kleene-star)
10. [$L \left(R^{*} \right) = \bigcup_{i \geq 0} {{L}^{i} \left(R \right)}$](#l-r-l-i-ge-0-l-i-r)
11. [tokens](#tokens)
12. [lexical analysis](#lexical-analysis)
13. [longest matching prefix rule](#longest-matching-prefix-rule)
14. [mariner 1](#mariner-1)
15. [lexical analysis continued](#lexical-analysis-continued)

###  language syntax

###  strings

###  languages

###  regular expressions

###  $L \left( R_{1} \mid R_{2} \right) = L \left( R_{1} \right) \cup L \left( R_{2} \right)$

###  $L \left( R_{1} \cdot R_{2} \right) = L \left( R_{1} \right) \cdot L \left( R_{2} \right)$

###  operator precedence

###  regular expressions

###  kleene star

###  $L \left(R^{*} \right) = \bigcup_{i \geq 0} {{L}^{i} \left(R \right)}$

###  tokens

###  lexical analysis

###  longest matching prefix rule

###  mariner 1

###  lexical analysis continued

## 01.2 - lexical analysis: regular expressions  

in lexical analysis, regular expressions are used as a way to represent tokens of a programming language

## 01.3 - lexical analysis: concatenation  

concatenation operation on regular expressions is defined as 

$L \left( R_{1} . R_{2} \right) = L \left( R_{1} . R_{2} \right)$

$R_1 \cdot R_2 = \{ xy \mid x \in R_1 \text{ and } y \in R_2 \}$

## 01.4 - lexical analysis: kleene star  

kleene star operator is an operation performed on regular expressions.  it is denoted as

$L \left( R^{*}\right) . \; L \left(R^{*} \right)= \{ \varepsilon \} \; \cup \; L\left(R\right) \cup \; L\left( R \right) . \; L\left( R \right) \cup L\left( R \right) . \; L\left( R \right) . \; L\left( R \right) \cup \cdots$

## 01.5 - lexical analysis: regular expression examples  

in this video we will see some examples of how regular expressions are used.

## 01.6 - lexical analysis: longest matching prefix rule  

longst matching prefix rule says that if there are more than one match, the longest match should be returned.  this is a way of resolving ambiguity when there are multiple matches.

## 01.7 - practice quiz  

the questions in this quiz are derived from the content presented in module 1.  the practice quiz is intended as a knowledge check for mastery of objectives in this module.  it provides a sample of questions you will see in the midterm exam for the course.

1.  consider the following code

```c++
Token LexicalAnalyzer::GetToken() {
    input.GetChar(c);
    switch (c) {
        case '=':
            input.GetChar(c);
            if (c == '=') {
                tmp.token_type = EQEQ;
            } else if
    }
}
```