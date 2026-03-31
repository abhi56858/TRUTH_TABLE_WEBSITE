# Boolean Logic Lab v2.0

A web-based tool designed to parse, evaluate, and visualize Boolean algebra expressions. This single-page application acts as both a truth table generator and an interactive logic circuit visualizer. 

## 🚀 Features

* Generates comprehensive truth tables for expressions containing up to 6 variables.
* Automatically renders dynamic logic circuit diagrams using HTML5 Canvas.
* Displays real-time statistics, calculating total rows, variables, and the exact count of True/False outcomes.
* Processes mathematical logic natively using a custom-built Lexer and Recursive Descent Parser.
* Gracefully catches invalid syntax and displays helpful error messages to the user.
* Features a highly stylized dark-mode UI with neon accents, animated grid backgrounds, and retro scanline overlays.

## 🧮 Supported Syntax

You can build complex expressions using a variety of text-based or symbolic operators. Parentheses `()` are fully supported for grouping.

**Standard Operators:**
* AND (`&&`)
* OR (`||`)
* NOT (`!` or `~`)
* XOR (`^`)
* NAND
* NOR
* XNOR

**Variables:**
* Standard variables use single letters from A-Z.
* The parser also supports full words as variables, as long as they do not conflict with reserved operator keywords.

## 🛠️ Technical Stack

This project is built to be lightweight and portable, requiring zero external dependencies or build tools.

* **Frontend:** Pure HTML5, CSS3, and Vanilla JavaScript.
* **Graphics:** Native HTML5 `<canvas>` API for rendering the circuit tree and logic gates.
* **Typography:** Utilizes 'JetBrains Mono' and 'Orbitron' via Google Fonts.

## 📥 Installation & Usage

Because this is a zero-dependency, single-file application, setup is instant.

1. Clone or download this repository to your local machine.
2. Open the `group_project.html` file directly in any modern web browser.
3. Type an expression into the input field (or click one of the provided examples) and click **Generate**.

## 🧠 Under the Hood

The application calculates the outputs by processing the input string through several stages:
1. **Lexer:** Scans the raw string and breaks it down into identifiable tokens (Variables, Operators, Parentheses).
2. **Parser:** Uses recursive descent to build an Abstract Syntax Tree (AST) based on standard order of operations (OR < XOR < AND < NOT).
3. **Evaluator:** Traverses the AST against every possible binary combination of variables to calculate the final truth table rows.
4. **Renderer:** Calculates spatial depth and positions for the AST nodes to draw connected logic gates on the HTML Canvas.
