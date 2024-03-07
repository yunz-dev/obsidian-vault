These lines define the main function.
This function is special as it is always the first line that runs in every rust executable
```rust
fn main() {
    println!("hi");
}
```
- declares a function called `main`, has no parameters and returns nothing
- parameters are declared inside the brackets
- rust requires `{}` around all function bodies
> A formatter tool called `rustfmt` can be used to format code 
- rust style is to indent with four spaces, not a tab
- something like `println!` calls a [[Rust Macro]]
- using `!` calls a macro and macros follow different rules to [[Functions]]
- most rust code end with semicolons 