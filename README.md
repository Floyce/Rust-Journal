#  Rust Learning Journal

Hey. I've decided to learn Rust from scratch this time. So I'll be documenting everything I learn as I work through the [Rustlings](https://github.com/rust-lang/rustlings) exercises. This repository serves as both my personal reference and a way to track my progress. I'm super excited to see where I'll be a year from now. Come with me. Lol;)

---

##  Progress Overview

| Day | Topics Covered | Status |
|-----|----------------|--------|
| **Day 1** | Setup, Variables, Functions |  Complete |
| **Day 2** | If Statements, Conditionals, Negation |  Complete |
| **Day 3** | Quiz 1 (Variables, Functions, If) |  Complete |
| **Day 4** | Move Semantics (Ownership) |  In Progress |

---

##  Setup Commands

```bash
# Install Rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Install rustlings
cargo install rustlings

# Start the exercises
rustlings

# Get a hint
rustlings hint <exercise_name>
Day 1: Variables & Functions
Variables
Declared with let

_Immutable by default (use mut to make mutable)_

**Must be initialized before use**

rust
let x = 5;          // Immutable
let mut y = 10;     // Mutable
y = 15;             //  Works

Shadowing
Reusing a variable name creates a new variable that hides the old one.

rust
let x = "hello";
let x = 5;          // x is now an integer
Constants
Declared with const

_Always need a type annotation_

**Naming convention: UPPERCASE_WITH_UNDERSCORES**

rust
const MAX_USERS: u32 = 100;
Functions
Defined with fn

**Parameters require type annotations**

**Return type specified with ->**

rust
fn add(x: i32, y: i32) -> i32 {
    x + y           // Implicit return (no semicolon)
}
**Statements vs. Expressions**
Type	Has Semicolon?	Returns?
Statement	 ;	Nothing (())
Expression No semicolon	A value

**Common Rust Types**
Type	Description
i32	Signed 32-bit integer (default)
u8	Unsigned 8-bit integer (0-255)
f64	Double-precision float
bool	true or false
char	Single Unicode character
String	Owned, growable text
&str	Immutable, borrowed text

**Day 2: If Statements**
_Key Concepts_
if is an expression (it returns a value)

Conditions must be bool (no implicit truthiness)

Both branches must return the same type

rust
let x = 5;
let result = if x > 3 { 10 } else { 0 };
// result = 10
The Negation Operator !
Flips a boolean value:

rust
let is_morning = true;
let is_evening = !is_morning;  // false
If-Else If-Else Chains
rust
let x = 5;

if x > 10 {
    println!("x is big");
} else if x > 5 {
    println!("x is medium");
} else {
    println!("x is small");
}

**Day 3: Quiz 1**
_What I Learned_
Module imports: use super::* imports items from the parent module into the child module

Parent/Child relationship: The test module (mod tests) can access functions defined in the parent scope

Function naming must match what the tests expect

The Apple Price Function
rust
fn calculate_price_of_apples(apples: i32) -> i32 {
    if apples <= 40 {
        apples * 2   // 2 rustbucks per apple
    } else {
        apples       // 1 rustbuck per apple
    }
}
Test Module Structure
rust
#[cfg(test)]
mod tests {
    use super::*;  // Import parent items

    #[test]
    fn verify_test() {
        assert_eq!(calculate_price_of_apples(35), 70);
        assert_eq!(calculate_price_of_apples(40), 80);
        assert_eq!(calculate_price_of_apples(41), 41);
        assert_eq!(calculate_price_of_apples(65), 65);
    }
}
Key Takeaway: The function in the parent module must have the exact same name that the tests are expecting.

 Next Up: Move Semantics (Ownership)
Coming soon: The heart of Rust's memory management system. Excitedd

 Resources
The Rust Book

Rustlings GitHub

Rust by Example

Docs.rs
