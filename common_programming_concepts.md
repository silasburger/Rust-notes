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


###Data Types
Every value in Rust has a specific data type.

Two important data type categories are *scalar* and *compound*.  

Rust is statically typed so you must know the type of all variable at compile time. The compiler can sometimes infer the type based on the value, but in cases when multiple types are possible you must add an annotation. Example:

```rust
let guess: u32 = "42".parse().expect("Not a number");

```

###Scalar Types
A single value. Not a complex data type. Rust has four primary scalar types:  
- Integers
- Floating point numbers
- Booleans
- characters

###Integer Types
A number without a fractional component. Example integer type declaration:

```rust
let num: i32 = 23;
```

The number dictates how many bits the integer takes up. The letter indicates if the integer is signed or unsigned ( i = signed, u = unsigned ). Unsigned values are always positive while signed types can be negative. Unsigned don't need a positive or negative sign. Signed values need a positive or negative sign.  

`Each signed variant can store numbers from -(2^(n - 1)) to 2^(n - 1) - 1 inclusive, where n is the number of bits that variant uses.`

i8 = -(2^7) to 2^7-1 OR -128 - 127

`Unsigned variants can store numbers from 0 to (2^n) - 1`

u8 = 0 to (2^8)-1 or 255  


isize and usize change depending on the computer that is running. 32 bit if you are using a 32 bit architecture and 64 if you are using a 64 bit architecture.

i32 is the default for integers.

###Integer Overflow
If you go over the specified type, this is called Integer Overflow. In debug mode this will trigger a *panic* (an error in compile mode). When compiling a release build rust will do *"twos complement wrapping"*. If you assign 256 to a u8 (max 255) then it will become 0, 257 will become 1, 258 will become 2, etc. 




















  
