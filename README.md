## 1. Getting Started

### 기초 명령어

- build your project with `cargo build`
- run your project with `cargo run`
- test your project with `cargo test`
- build documentation for your project with `cargo doc`
- publish a library to crates.io with `cargo publish`
- cargo new hello-rust

### Adding dependencies

Let’s add a dependency to our application. You can find all sorts of libraries on crates.io, the package registry for Rust. In Rust, we often refer to packages as “crates.”

1. we’ll use a crate called `ferris-says`.
   ```
       // Cargo.toml
       [dependencies]
       ferris-says = "0.2"
   ```
2. `cargo build`
