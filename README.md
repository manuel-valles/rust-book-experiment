# The Rust Programming Language

A playground and a guide for learning the Rust programming language. Based on the [Rust Book experiment](https://rust-book.cs.brown.edu/).

## Installation

- _Windows_: https://www.rust-lang.org/tools/install
- _Mac_: `$ curl --proto '=https' --tlsv1.3 https://sh.rustup.rs -sSf | sh`

Once you have it on your favourite OS, it can be updated or uninstalled by typing:

- `$ rustup update`
- `$ rustup self uninstall`

> Basic setup and extension for VSCode <3 https://code.visualstudio.com/docs/languages/rust

## Getting started

The toolset **Rustup** includes the `rustc` compiler, the `rustfmt` source code formatter, and the `clippy` Rust linter. You also get `Cargo`, the Rust package manager, to help download Rust dependencies and build and run Rust programs.

A good way to create your first Rust program is to use Cargo to scaffold a new project by typing `$ cargo new`. This will create a simple _Hello World_ program along with a default `Cargo.toml` dependency file. You pass cargo new the folder where you would like to create the project, e.g. `$ cargo new hello_world`

More Cargo commands:

- `$ cargo build` -> Build your Rust project
- `$ cargo run` -> Run your Rust project (This will compile/build it first if you haven't run the previous command)

> `!` means that you're calling a _macro_ instead of a normal function, and that macros don't always follow the same rules as functions.

> If you started a project that doesn't use Cargo, you can convert it to a project that does use Cargo. Move the project code into the `src` directory and create an appropriate `Cargo.toml` (_Tom’s Obvious, Minimal Language_) file.

> You could also compile it using the Rust compiler by entering the `rustc` command and passing it the name of your source file, e.g.: `$ rustc ./src/main.rs `. And finally you would run it with: `$ ./main`.
