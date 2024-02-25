# Rust


* [Rust language](https://www.rust-lang.org/)
* [Clippy documentation](https://doc.rust-lang.org/stable/clippy/usage.html)
* [Clippy source](https://github.com/rust-lang/rust-clippy)


## Hello world

```rust
fn main() {
    let name = "Foo Bar";
    println!("Hello, {name}!");
}
```

```
cargo new hello_world
cargo run
cargo build
cargo build --release

cargo clippy
cargo clippy -- -D clippy::pedantic
cargo clippy --fix
```

## Convert string to number, error handling

```rust
fn main() {
    let input = "420x";
    //let number: i32 = input.parse().unwrap();

    let number: i32 = match input.parse() {
        Ok(val) => val,
        //Err(err) => panic!("not good {err}"),
        Err(err) => {
            eprintln!("not good {err}");
            std::process::exit(1);
        },
    };

    dbg!(number);
}
```