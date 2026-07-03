# Lox Interpreter (Crafting Interpreters – Java Implementation)

This project is a Java implementation of the Lox language from the book *Crafting Interpreters* by Robert Nystrom. It includes a lexer (scanner), parser, AST generator, AST printer 
and a tree-walk interpreter.

## Features

- Lexical analysis (tokenizer/scanner)
- Recursive descent parser
- Abstract Syntax Tree (AST) generation
- AST Printer (debugging tool)
- Tree-walk interpreter
- Supports:
  - Arithmetic expressions (`+ - * /`)
  - Comparisons (`> < >= <=`)
  - Equality (`== !=`)
  - Unary operators (`! -`)
  - Grouping (`()`)
  - Literals (numbers, strings, booleans, nil)
  - String concatenation
  - Interactive REPL
  - Script execution from file

---

## Project Structure
os-project/
├── lox/
│ ├── Lox.java # Main entry point (REPL / file runner)
│ ├── Scanner.java # Lexer (tokenizer)
│ ├── Parser.java # Recursive descent parser
│ ├── Interpreter.java # Tree-walk interpreter
│ ├── AstPrinter.java # Debug AST printer
│ ├── Expr.java # Generated AST definitions
│ ├── Token.java
│ ├── TokenType.java
│ └── RuntimeError.java # Runtime exceptions
│
├── tool/
│ └── GenerateAst.java # AST code generator
│
└── README.md


---

## How to Build

From the project root:

### 1. Generate AST classes (if needed)
~bash
javac tool/GenerateAst.java
java tool.GenerateAst lox

This creates Expr.java.

2. Compile the project
javac lox/*.java
How to Run
Start REPL (interactive mode)
java lox.Lox

Example:

> 1 + 2 * 3
7
> !(5 > 2)
false
Run a script file

Create a file:

print 1 + 2;
print 5 * 10;

Run:

java lox.Lox filename.lox
Example Output
Input	Output
1 + 1	2
5 * 6	30
10 / 2	5
!(3 > 2)	false
"a" + "b"	ab
Notes
This is a tree-walk interpreter, so it is not optimized for performance.
Errors are reported with line numbers.
The project follows the structure of Crafting Interpreters closely.

License

For educational use only.
