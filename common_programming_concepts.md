#Common Programming Concepts

###Keywords
List of names that are offlimits to use as identifiers. Let, match are examples.

###Identifiers
First character is a letter, remaining characters are letters, numbers, or _s.  

***OR***

First character is a _ and there is more than one character that are letters, numbers, or _s.

###Raw
functions from other languages should use r# in front of identifier if it is using a offlimits keyword in Rust.

###Variables and Mutability
Variables are immutable by default. *Why?*  
This is to improve readability and to avoid errors that come from mutating something on accedent.

###Variables vs Constants
Constants cannot be made mutable.  
Constants can be declared in any scope including global.  
Must annotate the type of value when declaring constants.  
Use uppercase with underscore to separate words. Use underscore with number to improve readability. ex: `const MAX_NUMBER: u32 = 100_000;`  
Very useful for tracking things in the global scope in the application domain. Constants are good for hardcoding values in one place so that you only need to change it in one place in the future.


###Shadowing
Shadowing is when you declare a variable with the same name as a previously declared variable. The second is shadowing the first.
Example: 
```rust
fn main() {
    let x = 5;

    let x = x + 1;

    let x = x * 2;

    println!("The value of x is: {}", x);
}
```  
This is different than making a variable mutable becuase an error is raised if we try to reassign the varible without the let keyword. Using the let keyword allows us to transform the variable, keeping it immutable.  

A huge difference is that when using shadowing you can change the variables type, but you cannot change a mutable variables type simply by mutating it.

For example, this is not chill:
```rust 
fn main() {
	let spaces = '     ';
	spaces = spaces.len();
}
```



  
