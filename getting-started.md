#Getting Started

### Creating a project with Cargo
```bash
$ cargo new name_of_project
$ cd name_of_project
```

### Building and running a cargo project
Run the following at the root of the project.
 
```bash  
$ cargo build  
```

Run this command to run the built project...

```bash
$ ./target/debug/name_of_project
```

or do both of these at the same time (done at root).

```bash 
$ cargo run
```

To check if code is compiling run, do this:

```bash 
$ cargo check 
```

This command quickly makes sure your code compiles but it doesn't produce and executable. It is faster than cargo run and is useful when tinkering with code.


To compile for release, do this:  

```bash
$ cargo build --release 
```

This take longer to compile but the executable is more performant.








