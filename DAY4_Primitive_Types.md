# Day 4: Primitive Types & `cfg`

- Hey, this is my Day4 of my Rust Journal.And i'm super excited because it's on primitive types which are considered the most basic types that Rust provides out of the box. Unlike in other languages, Primitive Types are embedded/build into the language(Rust) itself.
- If you ask me, that's super cool and efficient.

## What I Learned Today

### 1. `cfg` (Configuration)
- **`#[cfg(test)]`** = Only compiles when running tests
- **`use super::*`** = Imports items from the parent module into the child module
- The test module (`mod tests`) is a **child module** that can access functions from the **parent module**

### 2. Primitive Types Overview

| Type | What it holds | Example |
|------|---------------|---------|
| **Integers** | Whole numbers | `5`, `-3`, `42` |
| **Floats** | Decimal numbers | `3.14`, `-2.5` |
| **Booleans** | True or false | `true`, `false` |
| **Characters** | Single Unicode char | `'a'`, `'😊'`, `'你'` |

### 3. Characters (`char`)

- **Single quotes** `' '` for characters
- **Double quotes** `" "` for strings
- Supports **Unicode** (emojis, foreign characters)
- Useful methods: `.is_alphabetic()`, `.is_numeric()`

```rust
let my_first_initial = 'C';
if my_first_initial.is_alphabetic() {
    println!("Alphabetical!");
} else if my_first_initial.is_numeric() {
    println!("Numerical!");
} else {
    println!("Neither alphabetic nor numeric!");
}

4. Variables vs Functions vs Arguments
Concept	What it is	Example
Variable	Container for data	let x = 5;
Function	Reusable block of code	fn add(a, b) { a + b }
Argument	Value passed to a function	add(5, 3)
5. Quiz 1 - Apple Price Function
rust
fn calculate_price_of_apples(apples: i32) -> i32 {
    if apples <= 40 { apples * 2 } else { apples }
}
6. Test Module Structure
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
### 7. Arrays (`[T; N]`)

- **Compound type** (groups values)
- **Same type** for all elements
- **Fixed size** (cannot grow or shrink)

```rust
// Create an array with 100 elements, all set to 0
let a = [0i32; 100];

// Check the length
if a.len() >= 100 {
    println!("Wow, that's a big array!");
}
Array syntax breakdown:

[0i32; 100] = [initial_value; length]

0i32 = value (all elements start as 0)

100 = number of elements

Other array examples:

rust
let numbers = [1, 2, 3, 4, 5];      // Specific values
let zeros = [0; 50];                 // 50 zeros
let bools = [true; 10];              // 10 true values
8. Compound Types Summary
Type	Different Types?	Fixed Size?	Example
Tuple	✅ Yes	✅ Yes	(i32, f64, char)
Array	❌ No (same type)	✅ Yes	[i32; 100]

Progress
Rustlings: 20/94 exercises complete

Completed: Variables, Functions, If, Quiz 1

In Progress: Primitive Types
