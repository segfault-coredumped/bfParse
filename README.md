# CSC 135: Recursive Descent Parse Tree

## Overview

This project is a simple implementation of a recursive descent parser for Brainfuck-like programs. The parser interprets the input Brainfuck code, builds a parse tree, and then interprets the program according to the Brainfuck instructions.

### Main Components

- **Scanner Class**: A basic tokenizer that processes the input token stream.
- **Node Class**: A tree structure to represent parse tree nodes.
- **Parser**: A recursive descent parser that builds a parse tree for Brainfuck-like syntax.
- **Interpreter**: A simple interpreter that executes the parse tree and outputs the result.
- **Output**: A function to display the parse tree and the interpreted Brainfuck program.

## Features

- **Parse Tree**: The parser generates a recursive descent parse tree for valid Brainfuck-like programs.
- **Interpreter**: The interpreter executes the parsed program, manipulating memory and output as specified by the Brainfuck language.
- **Program Output**: The program outputs both the original Brainfuck code, the parse tree, and the result of running the program.

## Setup Instructions

### Prerequisites

- Python 3.x
- A text editor or IDE for Python development

### Installation

1. Clone this repository or download the project files.
2. Make sure you have Python 3.x installed.

### Running the Program

To run the program, simply execute the script:

```bash
python bfinterpret.py
```


### Example Output

```bash
Program source:
[+[----->++<]>++.-]

Program tree:
S(LS(S(L(S(LS(S(C(>[S(C(+(S(LS(λ))]))(C(-)S(LS(λ))]))])))))

Program run:
Hello
```


## `node` Class

The `node` class represents a node in the parse tree. Each node contains:

- `data`: The value associated with the node.
- `children`: A list of child nodes, if the node has children (for non-leaf nodes).

## `parseS`, `parseL`, `parseC` Functions

These functions implement the recursive descent parsing strategy for the Brainfuck-like grammar:

- `S`: Represents the start symbol of the language. It can recursively parse sequences of `C` (commands) or `L` (loops).
- `L`: Represents a loop enclosed by square brackets (`[]`).
- `C`: Represents a command, which can be one of `>`, `<`, `+`, `-`, `.`, or `,`.


## `interpret` Function

The `interpret` function recursively interprets the parsed tree. It handles all Brainfuck commands such as `+`, `-`, `>`, `<`, `.`, and `,`. It uses a memory array (`data`) to simulate the tape of a Brainfuck interpreter.

### `output` Function

The `output` function recursively prints the parse tree. It outputs the data and structure of the tree in a readable format.

### `main` Function

The `main` function:

- Reads the Brainfuck code from `bf2.txt`.
- Removes any non-Brainfuck characters (e.g., comments or whitespace).
- Parses the program using the `parse` function.
- Outputs the source code, the parse tree, and the result of running the program.


## License

This project is free to use for educational purposes.


