#  01 regular expressions 

######  [← back](../README.md) 

## table of contents   

<small>[overview](#overview)</small>  
<small>[outcomes/objectives](#outcomesobjectives)</small>  
<small>[activities](#activities)</small>  
<small>[textbook readings](#textbook-readings)</small>  
<small>[lexical analysis: language and syntax](#lexical-analysis-language-and-syntax)</small>  
<small>[lexical analysis: regular expressions](#lexical-analysis-regular-expressions)</small>  
<small>[lexical analysis: concatenation](#lexical-analysis-concatenation)</small>  
<small>[lexical analysis: kleene star](#lexical-analysis-kleene-star)  </small>  
<small>[lexical analysis: regular expression examples](#lexical-analysis-regular-expression-examples)</small>  
<small>[lexical analysis: longest matching prefix rule](#lexical-analysis-longest-matching-prefix-rule)</small>  
<small>[practice quiz](#practice-quiz)</small>  

##  powerpoint presentations

<details><summary><small>principles of programming languages</small></summary>

<br>  

<small>[principles of programming languages](#principles-of-programming-languages)</small>  
<small>[what is a programming language](#what-is-a-programming-language)</small>  
<small>[how does the computer understand your instructions](#how-does-the-computer-understand-your-instructions)</small>  
<small>[how do they work](#how-do-they-work)</small>  
<small>[compiler](#compiler)</small>  
<small>[relocation](#relocation)</small>  
<small>[linker](#linker)</small>  
<small>[loader](#loader)</small>  
<small>[create a process](#create-a-process)</small>  
<small>[overview of program interpretation](#overview-of-program-interpretation)</small>  
<small>[what makes a program valid?](#what-makes-a-program-valid)</small>  
</details>


<details><summary><small>lexical analysis</small></summary>  

<br>  

<small>[lexical analysis](#lexical-analysis)</small>  
<small>[language syntax](#language-syntax)</small>  
<small>[strings](#strings)</small>  
<small>[languages](#languages)</small>  
<small>[regular expressions](#regular-expressions)</small>  
<small>[$L \left( R_{1} \mid R_{2} \right) = L \left( R_{1} \right) \cup L \left( R_{2}\right)$](#l-r1-r2-l-r1-l-r2)</small>  
<small>[$L \left( R_{1} \cdot R_{2} \right) = L \left( R_{1} \right) \cdot L \left( R_{2}\right)$](#l-r1-r2-l-r1-l-r2)</small>  
<small>[operator precedence](#operator-precedence)</small>  
<small>[regular expressions](#regular-expressions-1)</small>  
<small>[kleene star](#kleene-star)</small>  
<small>[$L \left(R^{*} \right) = \bigcup_{i \geq 0} {{L}^{i} \left(R \right)}$](#l-r-l-i-ge-0-l-i-r)</small>  
<small>[tokens](#tokens)</small>  
<small>[lexical analysis](#lexical-analysis)</small>  
<small>[longest matching prefix rule](#longest-matching-prefix-rule)</small>  
<small>[mariner 1](#mariner-1)</small>  
<small>[lexical analysis continued](#lexical-analysis-continued)</small>
</details>  

##  overview  

lexical analysis is the process of checking the syntac of a given programming language.  in lexical analysis, regular expressions are used as a way to represent the tokens of a programming language.  longest matching prefix rule says that if there are more than one match, the longest match should be returned and is a way of resolving ambiguity when there are multiple matches. 

##  outcomes/objectives

1.  explain what lexical analysis is
2.  describe what regular expressions are
3.  describe the language of a regular expression
4.  describe the concatenation of kleene star operator of regular expressions
5.  write regular expressions for a given token
6.  apply the longest matching prefix rule

##  activities

[homework 1](./01-homework.md)  
[project 1](./01-project.md)  

for project 1 you will work on a programming project implementing a lexer to generate toakens as discussed in this chapter.  refer to the project manual for complete details and the accompanying zip file for the starter code with some implementation.  refer to the project manual (instructions and implementation guide) for submission details.

your submission will be checked for plagiarism.  refer to the asu integrity policy.  collaboration with peers, getting coding help from outsite, and copying code from online resources such as github repositories, course hero, and chegg are not allowed.  you are not allowed to share the code or host it in a public repository.

##  textbook readings

**programming languages: principles and practice**

- [ ] chapter 1 - introduction - section 1.1 origins of programming languages
- [ ] chapter 1 - introduction - section 1.4 language definition  
- [ ] chapter 1 - introduction - section 1.5 language translation
- [ ] chapter 6 - syntax - section 6.1 lexical structure of programming languages  

**compiler construction: principles and practice**

- [ ] chapter 2 - scanning - section 2.2 regular expressions

----------

##  lexical analysis: language and syntax 

overview of programming languages.

what is a programming language, how does it work, and how does the computer know what to do?  view the following powerpoint to learn more.  

##  principles of programming languages

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

<img src="./assets/compiler.svg" alt="compiler" style="width: 400px;"/>

###  relocation

-  table of pointers to lines of code that need linking to different libraries
    -  the symbolic references
-  a symbol table is also created in this step, which has information about the symbols and what functions have to be loaded for a given symbol.
-  

###  linker

uses relation table to find lines of code to be replaced and then uses the symbol tables to find which functions have to be used.

<img src="./assets/table.svg" alt="table" style="width: 400px;"/>

1.  create 1 output binary (merged), start at 0
2.  fix all local references with global relative addresses
3.  fix all symbolic refs

###  loader

<img src="./assets/loader.svg" alt="loader" style="width: 400px;"/>

takes the output of linker and copies them to memory

<img src="./assets/0-loader.svg" alt="0-loader" style="width: 400px;"/>

###  create a process

-  process control blocks `pcb`
   -  process id
   -  process counter = start address of code
   -  status register
-  put the `pcb` in the ready queue

###  overview of program interpretation

<img src="./assets/interpretation.svg" alt="interpretation" style="width: 400px;"/>

###  what makes a program valid?

1.  **syntax**  what does it mean to look like a valid program?
2.  **semantics**  what does it mean for a program to be valid?
3.  **correctness**  is the program the correct one for the job?

-------------

lexical analysis

a programming language must have a clearly specified syntax.  lexical analysis is the process of checking the syntax of a given programming language.  refer to the lexical analysis powerpoint and watch the video below for more information.

##  lexical analysis

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

## lexical analysis: regular expressions  

in lexical analysis, regular expressions are used as a way to represent tokens of a programming language

## lexical analysis: concatenation  

concatenation operation on regular expressions is defined as 

$L \left( R_{1} . R_{2} \right) = L \left( R_{1} . R_{2} \right)$

$R_1 \cdot R_2 = \{ xy \mid x \in R_1 \text{ and } y \in R_2 \}$

##  lexical analysis: kleene star  

kleene star operator is an operation performed on regular expressions.  it is denoted as

$L \left( R^{*}\right) . \; L \left(R^{*} \right)= \{ \varepsilon \} \; \cup \; L\left(R\right) \cup \; L\left( R \right) . \; L\left( R \right) \cup L\left( R \right) . \; L\left( R \right) . \; L\left( R \right) \cup \cdots$

##  lexical analysis: regular expression examples  

in this video we will see some examples of how regular expressions are used.

##  lexical analysis: longest matching prefix rule  

longst matching prefix rule says that if there are more than one match, the longest match should be returned.  this is a way of resolving ambiguity when there are multiple matches.

##  practice quiz  

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


#  chapter 1 - introduction

##  section 1.1 origins of programming languages


##  section 1.4 language definition  
##  section 1.5 language translation

#  chapter 6 - syntax

##  section 6.1 lexical structure of programming languages  

#  chapter 2 - scanning

##  section 2.2 regular expressions