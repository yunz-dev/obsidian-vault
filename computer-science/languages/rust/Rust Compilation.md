***
Before running a [[Rust Program]], you have to [[Compile]] it using the [[Rust Compiler]], [[Rustc]]. E.g
```bash
rustc main.rs
```
This is similar to [[GCC]] and [[CLANG]]. When successful, rust outputs a binary executable.

The program can be run with
```bash
./main
```
Just compiling with [[Rustc]] is fine for simple programs, but as the project grows other ways to manage options and share code are needed. [[Cargo]]