---

# 🦎 MyLox — A Simple Interpreter (Java Implementation)

This project is an implementation of the **Lox language scanner (lexer)** in Java — based on the *Crafting Interpreters* book by **Robert Nystrom**.

It currently supports **lexical analysis**, which means it reads a `.lox` source file (or input from the console), breaks it into **tokens**, and prints them out.
This is the **first phase** of building a full interpreter.

---

## 📁 Project Structure

```
src/
└── com/
    └── jay/
        └── me/
            ├── Lox.java          # Main entry point (REPL + file runner)
            ├── Scanner.java      # Tokenizer that converts source code into tokens
            ├── Token.java        # Representation of a single token
            └── TokenType.java    # Enum listing all supported token types
```

---

## 🚀 Features

✅ Command-line tool that can:

* Run `.lox` files directly
* Enter interactive **REPL** mode (line-by-line execution)

✅ Performs lexical analysis:

* Identifies **keywords, identifiers, numbers, strings**, and **operators**
* Handles **comments** (`// ...`)
* Supports **error reporting** with line numbers

✅ Outputs a list of tokens in a human-readable format.

---

## 🧩 How It Works

1. **Lox.java**

   * Entry point of the interpreter.
   * Runs in two modes:

     * `jlox [script]` → Executes a Lox script file.
     * `jlox` → Starts the REPL prompt.

2. **Scanner.java**

   * Reads the source code character by character.
   * Groups characters into meaningful tokens.
   * Recognizes keywords, literals, symbols, and comments.

3. **Token.java**

   * Represents each token with:

     * `type` (from `TokenType`)
     * `lexeme` (the actual string)
     * `literal` (parsed value, if any)
     * `line` (for error tracking)

4. **TokenType.java**

   * Enum listing all possible token categories — punctuation, operators, literals, and reserved words.

---

## 🧠 Example Usage

### Run a `.lox` File

```bash
$ javac com/jay/me/*.java
$ java com.jay.me.Lox example.lox
```

### Interactive REPL Mode

```bash
$ java com.jay.me.Lox
> var x = 10;
VAR var null
IDENTIFIER x null
EQUAL = null
NUMBER 10 10.0
SEMICOLON ; null
EOF  null
>
```

---

## 🪄 Example `example.lox` File

```lox
var message = "Hello, world!";
print message;
```

Output:

```
VAR var null
IDENTIFIER message null
EQUAL = null
STRING "Hello, world!" Hello, world!
SEMICOLON ; null
PRINT print null
IDENTIFIER message null
SEMICOLON ; null
EOF  null
```

---

## 🧱 Next Steps (Future Work)

* Add a **Parser** for syntactic analysis
* Build an **AST (Abstract Syntax Tree)**
* Implement an **interpreter** for execution
* Add **runtime error handling**

---

## 📜 Credits

* Inspired by [Crafting Interpreters](https://craftinginterpreters.com/) by **Robert Nystrom**

---
