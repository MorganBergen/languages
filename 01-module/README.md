#  01 regular expressions

[content](../README.md)  
[01.0 - overview](#010---overview)  
[01.1 - lexical analysis: language and syntax](#011---lexical-analysis-language-and-syntax)  
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

lecture videos  
[powerpoint presentation](./powerpoint.md)
homework 1  
project 1  
practice quiz  

for project 1 you will work on a programming project implementing a lexer to generate toakens as discussed in this chapter.  refer to the project manual for complete details and the accompanying zip file for the starter code with some implementation.  

## 01.1 - lexical analysis: language and syntax  

## 01.2 - lexical analysis: regular expressions  

## 01.3 - lexical analysis: concatenation  

concatenation operation on regular expressions is defined as L(R1 • R2) = L(R1) • L(R2) and R1 • R2 = { xy : \in R1 & y \in R2 }

## 01.4 - lexical analysis: kleene star  

## 01.5 - lexical analysis: regular expression examples  

## 01.6 - lexical analysis: longest matching prefix rule  

## 01.7 - practice quiz  


Textbook Readings [Optional]:
Chapter 1- Introduction,
Section 1.4 'Language Definition' 

Chapter 6- Syntax 
Section 6.1- Lexical Structure of Programming Languages

 
Supplement Reading [Optional]:
From Compiler Construction- Principles and Practice, 
Chapter 2-  Scanning:
Section 2.2  Regular Expressions


Read Chapter 1- Introduction in the textbook, especially Sections 1.1- The Origins of Programming Languages, 1.4-Language Definition, 1.5 - Language Translation  for the topics covered in the slides 'Overview for programming Languages'. 
