# Theory of Computation
## Introduction
Theory of computation (also known as automata theory) is a theoretical branch of computer science and mathematics which mainly deals with logic of computation with respect to simple machines, referred to as automata.

Fundamental Capabilities and limitations of computers-
1. [[Automata]]
2. [[Computability]]
3. [[Complexity]]

``Symbol-->Alphabet-->String-->Language
``

## Symbol
Symbol is a the smallest building block, which can be numbers, letters, or even pictograms.
**Symbol**= {a,b,c,...,1,2,3,...A,B,C,...,@,#,$,...}
---
## Alphabet($\Sigma$)
Alphabets are the set of symbol, which are always finite.
$\Sigma$={1,2,3,4}, where |$\Sigma$|=4
$\Sigma$={a,b,c,....z}
$\Sigma$={d,f,k}, where |$\Sigma$|=3
> [!Summary]
>- Set of symbol
>- Alphabets are denoted by sigma($\Sigma$)
>- Number of the symbols of the Alphabet is denoted by |$\Sigma$|
>- Finite
### Power of $\Sigma$
$\Sigma^1$= ==set of all strings of size 1 over alphabet $\Sigma$==	
$\Sigma^2$= ==set of all strings of size 2 over alphabet $\Sigma$==	
$\Sigma^3$= ==set of all strings of size 3 over alphabet $\Sigma$==	
$\Sigma^0$= =={$\epsilon$} [Empty set, cause string size= 0]==
$\Sigma^*$= ==$\Sigma^0U\Sigma^1U\Sigma^2U\Sigma^3+....$== [Mother of all strings]

Let's consider alphabets,
$\Sigma$={a,b,c}
>In $\Sigma^2$, possible combinations,
>$|\Sigma|^2$
>$3^2$ = 9 combinations [Where length of each string is 2]

>So,
>$\Sigma^2$= {aa,ab,ba,bb,ac,ca,bc,cb,cc}
---
## String(**w**)
A string is a finite sequence of symbols from some alphabet. 
If the number of symbols in the alphabet is |$\Sigma$|=3 and length of string, **n**=2 then,
The number of strings of length **n** possible = $|\Sigma|^n$
=$3^2$ =6
>[! Summary ]
>- String is denoted by **w**.
>- The length of string is denoted by |**w**|.
>- String can be empty, which is denoted by $\epsilon$(Epsilon)
## Language
A language is a set of strings, chosen from some Alphabets($\Sigma$).
**Example**:
Consider alphabets, $\Sigma$={a,b}
- L1 is defined over alphabets $\Sigma$
  L1={w|w starts with 'b'}
   So, L1={b,bba,bbb,bab,bbabb,baab,...}-->Infinite Language
- L2={w| Length of w is 2}
  So, L2= {aa,ab,ba,bb}----> Finite Language
> [!Summary]
>- Language can be finite or infinite
### Finite State Machine
|$\Sigma$|Alphabet|
|--------|----------|
| **Q**|States |
|$?$|Transition|
|**$Q$**|Start State|
|**F**|Accepted State|

[[Finite State machine examples]]
