# The Rust Programming Language

A playground and a guide for learning the Rust programming language. Based on the [Rust Book experiment](https://rust-book.cs.brown.edu/).

## Installation

- _Windows_: https://www.rust-lang.org/tools/install
- _Mac_: `$ curl --proto '=https' --tlsv1.3 https://sh.rustup.rs -sSf | sh`

Once you have it on your favourite OS, it can be updated or uninstalled by typing:

- `$ rustup update`
- `$ rustup self uninstall`

> Basic setup and extension for VSCode <3 https://code.visualstudio.com/docs/languages/rust

## Getting Started

The toolset **Rustup** includes the `rustc` compiler, the `rustfmt` source code formatter, and the `clippy` Rust linter. You also get `Cargo`, the Rust package manager, to help download Rust dependencies and build and run Rust programs.

A good way to create your first Rust program is to use Cargo to scaffold a new project by typing `$ cargo new`. This will create a simple _Hello World_ program along with a default `Cargo.toml` dependency file. You pass cargo new the folder where you would like to create the project, e.g. `$ cargo new hello_world`

More Cargo commands:

- `$ cargo build` -> Build your Rust project
- `$ cargo run` -> Run your Rust project (This will compile/build it first if you haven't run the previous command)

> `!` means that you're calling a _macro_ instead of a normal function, and that macros don't always follow the same rules as functions.

> If you started a project that doesn't use Cargo, you can convert it to a project that does use Cargo. Move the project code into the `src` directory and create an appropriate `Cargo.toml` (_Tom’s Obvious, Minimal Language_) file.

> You could also compile it using the Rust compiler by entering the `rustc` command and passing it the name of your source file, e.g.: `$ rustc ./src/main.rs `. And finally you would run it with: `$ ./main`.

## Basics by Example: Programming a Guessing Game

- The `std` or **standard library** brings a set of items into the scope of every program. This set is called the _prelude_. If you need to use a type that it isn't in the prelude, you can bring it into the scope explicitly with a `use` statement:

  - `use std::io`

- To be able to create a variable in Rust you will need `let` statement. However, if you want to make it mutable adding `mut` before the variable name (**Rust variables are immutable by default**):

  - `let my_variable = 1;`
  - `let mut my_mutable_variable = 1`;

- The syntax `String::new` means a function that returns a new instance of a `String`. `String` is a string type (UTF-8 encoded bit of text) provided by the std library. For example:

  - `let mut guess = String::new();` creates a mutable variable that is bound to a new, empty instance of a `String`

- `io::stdin().read_line(&mut guess)` calls the `read_line` method on the standard input handle to get input from the user, and the argument `&mut guess` is passed to tell it what string to store the user input in. However, this doesn't overwrite its contents. That's why the string argument needs to be mutable so the method can change the string’s content.

> The `&` indicates that this argument is a reference, which gives you a way to let multiple parts of your code access one piece of data without needing to copy that data into memory multiple times.

> If we don't import the `io` library with `use std::io` at the beginning of the program, we could still use the function by writing this function call as `std::io::stdin`. The stdin function returns an instance of `std::io::Stdin`, which is a type that represents a handle to the standard input for your terminal.

- `io::stdin().read_line(&mut guess).expect("Failed to read line");` is an instance of `Result` that has an `expect` method that you can call:

  - If this instance of Result is an `Err` value, `expect` will cause the program to crash and display the message that you passed as an argument to expect
  - If this instance of Result is an `Ok` value, `expect` will take the return value that `Ok` is holding and return just that value to you so you can use it

> If you don’t call expect, the program will compile, but you’ll get a warning!!
> It's often wise to introduce a newline and other whitespace to help break up long lines when you call a method.
> `Result` is an ` enumeration``enum ` what is a type that can be in one of multiple possible _states/variants_.
