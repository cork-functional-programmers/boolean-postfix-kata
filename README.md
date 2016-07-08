# Boolean-Postfix Kata

## Postfix notation

Logical Boolean expressions are typically written using infix notation,
but an alternative called "postfix notation” exists.

In infix notation,

- binary operators (∧, ∨, ⊕, etc.) are placed between their operands;
- the ¬ unary operator is placed before its operand;
- parentheses are used to indicate precedence.

Here is a Boolean expression written in infix notation:

> (a ∧ b) ∨ ¬ c

It evaluates to true if both `a` and `b` are true, or if `c` is false.
By contrast, in postfix notation,

- an operator is placed after its operand(s);
- parentheses are not needed.

Here is the same Boolean expression as above, written in postfix notation:

> a b ∧ c ¬ ∨

## Your task

Write a function that takes a string corresponding to a Boolean expression written in postfix notation,
parses that expression and evaluates it. The choice of the programming language is up to you.
You may choose to exercise your function in the REPL (if one is available for your language),
or produce an executable and run it at the command line.

### Input

A string corresponding to a Boolean expression written in postfix notation.
For the sake of simplicity, you can assume that input strings all correspond to valid Boolean expressions.
Each token is separated by a single space character. The possible tokens are

- `0` for false,
- `1` for true,
- `A` for AND,
- `R` for OR,
- `X` for XOR (exclusive-or),
- `N` for NOT.

### Output

`true` if the expression evaluates to true; `false` otherwise.

## Test cases

Here are some sample inputs/outputs. Feel free to use them in your unit tests.

    Input                Output
    0 1 R                true
    0 0 R                false
    1 0 A 1 R N N        true
    0 0 A 0 N 0 N A R    true
    0 1 A 0 N 1 N A R    false
    1 0 A 1 N 0 N A R    false
    1 1 A 1 N 1 N A R    true
    1 1 A 1 N 1 N A X    true
    1 1 A 0 N 0 N A X    false
