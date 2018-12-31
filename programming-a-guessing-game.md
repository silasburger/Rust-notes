#Programming a guessing game

###Starter code
The following code was given to explain a variety of simple rust concepts.

```rust
use std::io;

fn main() {
    println!("Guess the number!");

    println!("Please input your guess.");

    let mut guess = String::new();

    io::stdin().read_line(&mut guess)
        .expect("Failed to read line");

    println!("You guessed: {}", guess);
}

```

###The Prelude###
The prelude is a the standard library for Rust. The prelude brings a select few types into scope of every program. If a type isn't in the prelude you must bring that type into scope with a use statement.

***use std::io***  
- Use io crate from standard library.
  
***let mut guess***  
- let declares a variable  
- variables are immuatable by default  
- use mut to make a variable mutable  

***String::new()***  
- new instance of `String`  
- `String` is from standard library that is a growable, UTF-8 encoded bit of text.  
- The `::` indicates that new is an associated function of the `String` type. Other languages call this a *static method*.

***io::stdin().read_line(&mut guess)***  
- `std::io::stdin` is the same as io::stdin with use std::io at top  
- The read_line takes the user input an places it in a string. It take the string to place it in as reference.  
- The `&` is a reference. A reference is when you want multiple parts of your code to access a one piece of data from a single place in memory without copying it to memory multiple times.
- `read_line` also returns a value which is a `Result` type.  
- Rust has a number of types named `Result`. The generic `Result` type and `Result` types for specific submodules. ie. `io::Result`.
- `Result` types are enumeration (*enums*). An enumeration is a type that has a fixed set of values.

***.expect("Failed to read line");***  
If `read_line` returns an Err for its Result (an enum), then expect crashes the program and prints the message. Expect is a method on the Result type.


***cargo.lock***  
Cargo.lock holds the correct versions of all the program dependencies. This allows us to make a reproducible build, even if dependencies update automatically.

***cargo update***  
This updates all the dependencies to the newest version and updates the cargo.lock. The update will stay within one point of the version that you were using previously. If you are on 3.14 and there is a 3.15 & 4.0 it will update to 3.15.

###cargo doc --open###
This command, `cargo doc --open`, generates a web page containing documentation for the dependencies that you have created. This is super useful.








