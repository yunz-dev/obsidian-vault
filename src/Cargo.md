***
[Documentation](https://doc.rust-lang.org/cargo/)
Cargo is the [[Build System]] and [[Package Manager]] for [[Rust]].
- Builds codes
- Downloads [[Libraries]] and [[Dependencies]]
- Builds [[Libraries]] and [[Dependencies]]
Check Cargo version with
```bash
cargo --version
```
You can create a new [[Project]] in Cargo with:
```bash
cargo new project_name
```
This creates a new [[Directory]] and [[Project]] called `project_name` and creates project files into the directory `Cargo.toml` and `src/main.rs`
Cargo should also automatically intialise a new [[Git]] [[Repository]] along with a `.gitignore` file. 
- This doesn't happen if `cargo new` is run within an existing [[Git]] [[Repository]].
- This can be overridden with `cargo new --vcs=git`
- [[Cargo.toml]]
- [[Cargo]] expects [[Source Files]] to be stored under the `src` [[Directory]]
- Top level [[Directory]] is for:
	- [[README]] files
	- [[Licence]]'s
	- [[Configuration]] Files
	- Anything else that isn't code
Cargo is essential for organising projects
- you can convert stray project files into a project by moving the project code into the [[Source Files]] [[Directory]] and creating an appropriate [[Cargo.toml]] file.

## Building and Running a Cargo Project
From the [[Project]] [[Directory]] run:
```bash
cargo build
```
- [[Cargo]] won't [[Compile]] the program if no changes are made
This creates an [[Executable]] at `target/debug/project_name`. This is because the default build is a [[Debug Build]].
Run the [[Executable]] with:
```bash
./taget/debug/project_name
```
Command to build, then execute
```bash
cargo run
```
Command to use to check if it compiles, without building:
```bash
cargo check
```
> This is faster than building
> Should be used periodically

When the project is ready for [[Final Release]], you can use:
```bash
cargo build --release
```
This compiles with optimisations and creates an [[Executable]] at `target/release`
- This takes longer to build, but runs faster