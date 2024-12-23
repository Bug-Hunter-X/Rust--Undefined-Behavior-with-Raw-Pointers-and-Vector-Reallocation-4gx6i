# Rust: Undefined Behavior with Raw Pointers and Vector Reallocation

This repository demonstrates a common source of undefined behavior in Rust: manipulating a vector's data through a raw pointer after the vector has reallocated its memory. Modifying the data in this scenario can result in unpredictable behavior, including crashes and data corruption. The example highlights the importance of careful memory management when using raw pointers in Rust and encourages the use of safe methods whenever possible.

## Bug Description
The `bug.rs` file contains Rust code that attempts to modify a vector's contents using a raw pointer.  After modifying the value, the code prints the modified vector.  However, if the vector reallocates memory (e.g., due to adding more elements), the pointer becomes invalid.  Attempting to dereference this invalid pointer results in undefined behavior.

## Solution
The `bugSolution.rs` file shows a safe alternative. It demonstrates how to correctly update vector elements without resorting to raw pointers. This prevents undefined behavior and ensures data integrity.