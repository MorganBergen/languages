#  languages

##  [**01 regular expressions**](01-module/README.md)  
[01.0 - overview](01-module/README.md#010---overview)  
[01.1 - lexical analysis: language and syntax](01-module/README.md#011---lexical-analysis-language-and-syntax)  
[01.2 - lexical analysis: regular expressions](01-module/README.md#012---lexical-analysis-regular-expressions)  
[01.3 - lexical analysis: concatenation](01-module/README.md#013---lexical-analysis-concatenation)  
[01.4 - lexical analysis: kleene star](01-module/README.md#014---lexical-analysis-kleene-star)  
[01.5 - lexical analysis: regular expression examples](01-module/README.md#015---lexical-analysis-regular-expression-examples)  
[01.6 - lexical analysis: longest matching prefix rule](01-module/README.md#016---lexical-analysis-longest-matching-prefix-rule)  
[01.7 - practice quiz](01-module/README.md#017---practice-quiz)

---

**module 2: syntax and analysis parsing**  
2.0: overview  
2.1: introduction to syntax analysis  
2.2: context-free grammars  
2.3: leftmost & rightmost derivations  
2.4: parse tree  
2.5: ambiguous grammar  
2.6: efficient parsing  
2.7: first sets  
2.7.1: example – first sets  
2.8: follow sets  
2.8.1: example – follow sets  
2.9: conditions for predictive recursive descent parser  
2.10: writing a predictive descent parser  
2.11: practice quiz  

**module 3: basic semantics and pointer semantics**  
3.0: overview  
3.1: pointer semantics examples  
3.2: memory allocation and deallocation  
3.3: memory errors  
3.4: practice quiz  

**module 4: type systems**  
4.0: overview  
4.1: introduction to type systems  
4.2: name equivalence  
4.3: structural equivalence  
4.4: structural equivalence algorithm  
4.5: hindley-milner type interface  
4.6: implicit polymorphism part - 1  
4.7: implicit polymorphism part - 2  
4.8: practice quiz  

**module 5: lambda calculus**  
5.0: overview  
5.1: introduction to lambda calculus  
5.2: disambiguation rules  
5.3: semantics  
5.4: currying  
5.5: equivalence and renaming  
5.6: substitution  
5.7: execution  
5.8: practice quiz  

**module 6: runtime execution environment**  
6.0: overview   
6.1: the runtime environment  
6.2: local variables  
6.3: stack  
6.4: function frame  

##  information

**cse 340**  
principles of programming languages   

**arizona state university**   
 ira a. fulton schools of engineering   |  school of computing, informatics, and decision systems engineering  

**description**  
in this course, we will explore, formal syntactic and semantic descriptions, compilation and implementation issues, and theoretical foundations for several programming paradigms.  programming languages are one of the most important and direct tools for the construction of a computer system: in a modern computer, different languages are routinely used for different levels of abstraction. programming language is important because it defines the relationship, semantics, and grammar which allows the programmers to effectively communicate with the machines that they program. 

**instructors**  
| instructor | contact info | office hours | zoom link |
|------------|--------------|-------------|-----------|
| tejasvi parupudi, ph.d. | parupudi@asu.edu | tuesdays: 1:00 pm - 2:00 pm (az time) | https://asu.zoom.us/j/81748255312 |
| shravan swaminathan | sswami28@asu.edu | tuesdays: 11:00 am - 12:00 noon. (az time) | https://asu.zoom.us/j/5147971140 |

**objectives**  
| # | description |
|:-----------|:-------------|
| 1 | given a regular expression, dicern if a string matches a regular expression |
| 2 | given a context-free grammar, write a program to parse another program written following the context-free grammar |
| 3 | follow semantic rules to determine whether a sentence in a program has semantic meaning |
| 4 |  in a programming language, given a line, determine a definitive semantic meaning |
| 5 | navigate a typed system & determine type equivalence, recover unknown types through polymorphism, & determine type errors |
| 6 | use lambda calculus |
| 7 | amnipulate stack, heap, & memory at runtime |

**texts**   
|  title  | author | isbn |
|:---------|:--------|------|
|  programming languages: principles and practice |  kenneth c. louden and kenneth a. lambert | 9781111529413 |
|  compiler construction: principles and practice | kenneth c. louden |  0534939724 | 

**assessments & assignments**  
| due date           | name                | score    | percentage | sections |
|:-------------------|:--------------------|----------|------------|----------|
| june 03 by 1:59 am | homework 1          | - / 50   | 10%        |          |
| june 17 by 1:59 am | project 1           | - / 100  | 10%        | 1, 2, 3  |
| june 21 by 1:59 am | homework 2          | - / 100  | 10%        |          |
| june 22 by 1:59 am | midterm             | - / 80   | 20%        | 1, 2, 3  |
| june 23 by 1:59 am | midterm worksheet   | - / 0    | 0%         |          |
| july 01 by 1:59 am | project 2           | - / 100  | 10%        | 3, 4, 5  |
| july 12 by 1:59 am | project 3           | - / 100  | 10%        | 5, 6     |
| july 18 by 1:59 am | final exam          | - / 80   | 10%        | 5, 6     |
| unknown            | 4.8 practice quiz   | - / 5    | 10%        | 4        |
| unknown            | 5.9 practice quiz   | - / 6    | 10%        | 5        |

