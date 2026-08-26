# Day 4: Primitive Types & `cfg`

- Hey, this is my Day4 of my Rust Journal.And i'm super excited because it's on primitive types which are considered the most basic types thet Rust provides out of the box. Unlike in othere languageds, Primitive Types are embedded/build into the language(Rust) itself.😊If you ask me, that's super cool and efficient.

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
📊 Progress
Rustlings: 18/94 exercises complete

Completed: Variables, Functions, If, Quiz 1

In Progress: Primitive Types