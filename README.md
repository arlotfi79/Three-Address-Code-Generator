# Three-Address-Code-generator
This project was designed by [**Dr. Eghbal Mansoori**](https://ece.shirazu.ac.ir/en/~mansoori) for the Principles of Compiler Design course (Fall 2022).

## Description  
The goal of this project is designing a compiler that reads an expression and produces the three-address-code for it in C language so that the result of the expression is calculated when executed. 

* The expression includes integers and decimals, variables, parentheses, spaces and the following operators:
  - **:A:** for addition
  - **:S:** for subtraction
  - **:M:** for multiplication
  - **:D:** for division

* The priority of operators is as usual, but their associativity is the reverse of the usual.
* For each operator, the calculation of the operands is reversed, that is, the right and left operands are interchanged and calculated.
* It is assumed that the input statement has no compiler error.

## Tools
* Only three phases of **lexical analysis**, **syntax analysis**, and **intermediate code generation** should be designed.
* The design of the lexical analysis phase should be done using the **Lex** tool.
* **Yacc** tool should be used for syntax analysis phase and simultaneous translation to intermediate code.

## Example
| Input                         | Output                                          | 
| ----------------------------- |-------------------------------------------------|
| x = 3 :D: 4:S: 12             | t1 = 4/3; <br> x = 12-t1;                       |
| x = 3 :D: (4:S: 12)           | t1 = 12-4; <br> x = t1/3;                       |
| x = 36 :M: test :D: ps :A:123 | t1 = ps/test; <br> t2 = t1*36; <br> x = 123+t2; |

## How to use
* You only need to run the `script.sh` file (Required dependencies will be installed).
* You should input your expression in the command-line.
