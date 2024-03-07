```toml
[package]
name = "rust_project"
version = "0.1.0"
edition = "2024"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]

```
It is written in [[TOML]] format
- The first line, `[package]` is a section heading
	- the section contains statements for [[Package]] [[Configuration]]
- The `name`, `version` and `edition` are necessary for [[Cargo]] to [[Compile]] the [[Program]]
- `[dependencies]` section lists project [[Dependencies]]
	- [[Rust]] refers to [[Package]]s of [[Code]] as [[Crates]]