# Computer Science

## IDE (Integrated Development Environment)

- Features to write, translate, and run code.
- Debugging (find and fix bugs).
  - Bugs.
    - Mistakes in programs that cause them to behave differently than intended.
  - Debugger.
    - Walk through the program step-by-step.
    - Can inspect variables and other information while the program is running.
    - Breakpoint: a place, line of code, where we want the debugger to pause execution.
  - Rubber duck.

## Compiler (translate the code into binary or computer language)

- Assembly language.
- Linking.
  - The process of combining all the machine code files into a binary file.

## Command Line Interface

- Command-line argument.
- Exit status.
  - 0: nothing went wrong.

## Problem Solving

- Correctness (whether the code solves the problem correctly).
- Design (how efficient and readable the code is).
- Style (how well-formatted the code is visually).
- Source code (code that we can read and write).
- Algorithm.
  - Step-by-step instructions to solve a problem.
- Pseudocode.
  - Representation of an algorithm in precise human language.
- Abstraction.
  - The process of removing attributes, in objects or systems, to focus attention on details of greater importance.

## Programming Language

### Building blocks

#### Functions

    - Arguments or parameters, return values.
    - Process: arguments -> functions -> side effects (return values).

#### Conditionals

#### Boolean expressions

#### Loops

- For.
  - Só pode ser usado quando se sabe a quantidade de vezes que o loop vai acontecer.
- TODO: OUTROS LOOPS

#### Variables

    - Constant: a variable that cannot change.
    - Magic number: a value that comes from somewhere unknown.

#### Operators (+, -, \*, /, %)

    - Syntactic sugar (+=, -=, ++, --).

#### Library or Header file (C/C++)

    - Reusable common set of code.

## Character Encoding Standards

- ASCII (American Standard Code for Information Interchange).
  - Maps text characters for the computer.
  - Examples.
    - 0 -> 48.
    - A -> 65.
    - a -> 97.
- Unicode.
  - Uses more bits than ASCII to accommodate accent marks and symbols.

## Data Types

- Int (Integer).
  - Take up 4 bytes or 32 bits of memory, so it has limitations.
    - Integer overflow.
  - Goes from -2^31 to 2^31-1, roughly from negative 2 billion to positive 2 billion.
  - Qualifiers.
    - Unsigned.
      - No negative values.
      - Doubles the amount of positive integers.
    - Short.
    - Long.
    - Const.
- Char (Single character).
  - Take up 1 byte or 8 bits of memory, so it has limitations.
  - Goes from -128 to 128-1.
  - Positive numbers used in ASCII.
- Float (Floating Point Numbers or real numbers or numbers with decimal values).
  - Take up 4 bytes or 32 bits of memory, so it has limitations on its precision.
    - Floating-point imprecision.
  - Example: PI -> 3.141592 (seven digits of precision).
- Double (Floating Point Numbers on steroids).
  - Take up 8 bytes or 64 bits of memory, double precision of a float or close to 20 decimal digits.
- Bool (true or false).
  - Not present in C by default.
- String (a sequence or series of characters).
  - Examples: words, sentences, paragraphs and so on.
  - Not present in C by default.
  - Format codes: placeholders for string manipulation.
- Void (It is a type and not a data type).
  - Placeholder for nothing.
  - Used in functions.
    - List of parameters can be void or it takes no parameters.
    - To return an unspecified value.
- Structs.
  - Group data types into one unit.
- Typedefs.
  - Used to create custom data types.

## Variables

- Declaration: assign a data type and a name.
- Only use it as needed.
- Examples:
  - `int number = 42;`
  - `float sqrt2, sqrt3, pi;`
- You can declare and initialize a variable at the same time.

## Algorithms

- Search.
  - Linear.
    - Running time.
      - Upper bound: O(n).
      - Lower bound: Ω(1) or constant.
    - Pseudocode
      ```
      For each door from left to right
        If number is behind door
          Return true
      Return false
      ```
  - Binary.
    - Running time.
      - Upper bound: O(log n).
      - Lower bound: Ω(1) or constant.
    - Pseudocode
      ```
      If no doors
        Return false
      If number behind middle door
        Return true
      Else if number < middle door
        Search left half
      Else if number > middle door
        Search right half
      ```

## Memory

- Image.
  - Pixels.
    - 8 bit colors: RGB with values from 0 to 255.
- Hexadecimal.
  - Base-16 or 16 digits (0 1 2 3 4 5 6 7 8 9 A B C D E F).
  - Refer to memory address, ex: `0x7ffcb4578e5c`.
    - Segmentation fault: read or write to memory without permission.
    - Dereference operator (\*): get the value of an address.
  - Color code.
  - Two digits = a byte in binary.
- Pointer arithmetic.
  - Apply mathematical operations to pointers.
- Garbage values: unknown values in memory.
- Swap: change two memory values of place using a third address.
- Layout or memory sections.
  - Machine code: compiled program’s binary code.
  - Globals or global variables: declared a program.
  - Heap: empty area from where malloc can get free memory.
    - Heap overflow: too much memory allocated in the heap section.
  - Stack: used by functions and local variables.
    - Stack overflow: too much memory allocated in the stack section.
