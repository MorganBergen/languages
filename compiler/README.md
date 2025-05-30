#  scanning

######  compiler construction: principles and practice  

######  section 2.2 regular expressions (page 31 - 47)

##  introduction
<small>
the scanning or **lexical analysis**, phase of a compiler has the task of reading the source program as a file of characters and dividing it up into tokens.  tokens are like the words of a natrual language:  each token is a sequence of characters that represnts a unit of information in the source program.  typical examples are **keywords**, such as `if` and `while`, whcih are fixed strings of letters; **identifiers**, such are user-defined strings, usually consisting of letters and numbers and beginning with a letter; **special symbols**, such as the arithmetic symbols such as `+`, `*` or multicharacter symbols such as `>=`, `<>`.  in each case a token represents a certain pattern of characters that is recognized, or matched by the scanner from the beginning of the remaining input characters.

since the task performed by the scanner is a special case of pattern matching, we need to study methods of pattern specification and recognition as they apply to the scanning process.  these methods are primarily those of **regular expressions** and **finite automata**.  however, a scanner is also the part of the compiler that handles the input of the source code, and since this input often involves a significant time overhead, the scanner must operate as efficiently as possible.  thus, we need also to pay close attention to the practical details of the scanner structure.

we divide the study of scanner issues as follows.  first, we give an overview of the operation of a scanner and the structures and concepts involved.  then, we study regular expressions, a standard notation for representing the patterns in strings that form the lexical structure of a programming language.  following that, we study finite state machines, or finite automata, which represent algorithms for recognizing string patterns given by regular expressions.  we also study the process of constructing finite automata out of regular expressions.  we then turn to practical methods for writing programs that implement the recognition processes represented by finite automata, and we study a complete implementation of a scanner for the TINY language.  finally, we study the way the process of producing a scanner program can be automated through the ue of a scanner generator, and we repeat the implementation of a scanner for TINY using Lex, which is a standard scanner generator available for use on unix and other systems.
</small>

##  scanning process

<small>

it is the job of the scanner to read characters from the source code and form them into logical units to be dealt with by further parts of the compiler (usually the parser).  the logical units the scanner generates are called **tokens**, and forming characters into tokens is much like forming characters into words in an english sentence and deciding which word is meant.  in this it resembles the task of spelling.

tokens are logical entities that are usually defined as an enumerated type.  for example, tokens might be defined in C as

```C
typedef enum 
    {IF, THEN, ELSE, PLUS, MINUS, NUM, ID, ...}
    TokenType;
```

tokens fall into several categories.  these includ ethe reserved words, such as `IF` and `THEN`,  which represent the strings of characters `if` and `then`.  a second category is that of special symbols, such as the arithmetic symbols `PLUS` and `MINUS`, which represents the characters `+` and `-`.  finally, there are tokens that can represent multiple stings.  examples are `NUM` and `ID`, which represent numbers and identifiers.



</small>