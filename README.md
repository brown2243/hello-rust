## 1. Getting Started

### 기초 명령어

- build your project with `cargo build`
- run your project with `cargo run`
- test your project with `cargo test`
- build documentation for your project with `cargo doc`
- publish a library to crates.io with `cargo publish`
- `cargo new hello-rust`

### Adding dependencies

Let’s add a dependency to our application. You can find all sorts of libraries on crates.io, the package registry for Rust. In Rust, we often refer to packages as “crates.”

1. we’ll use a crate called `ferris-says`.
   ```
       // Cargo.toml
       [dependencies]
       ferris-says = "0.2"
   ```
2. `cargo build`

---

## 2. Programming a Guessing Game

```
use std::io;

<!-- 메인 함수 -->
fn main() {
    println!("Guess the number!");
    println!("Please input your guess.");

    <!-- 입력값을 저장할 변수 선언 -->
    let mut guess = String::new();

    io::stdin()
        .read_line(&mut guess)
        .expect("Failed to read line");

    println!("You guessed: {}", guess);
}

```

### let(variable)

입력값을 저장할 변수 선언
let statement, which is used to create a variable. Here’s another example:

```
    In Rust, variables are immutable by default.
    let foo = bar;
    let foo = 5; // immutable
    let mut bar = 5; // mutable
```

### String::new

a function that returns a new instance of a String. String is a string type provided by the standard library that is a growable, UTF-8 encoded bit of text.

To summarize, the let mut guess = String::new(); line has created a mutable variable that is currently bound to a new, empty instance of a String. Whew!
`let mut guess = String::new();`

### use std::io;

유저입력을 받는 기능을 불러옴
` io::stdin().read_line(&mut guess)`
use std::io; 선언을 안했다면, std::io::stdin 로 호출 가능
If we hadn’t put the use std::io line at the beginning of the program, we could have written this function call as std::io::stdin.

`.read_line(&mut guess)`,
calls the read_line method on the standard input handle to get input from the user. We’re also passing one argument to read_line: &mut guess.
`&`
The & indicates that this argument is a reference, which gives you a way to let multiple parts of your code access one piece of data without needing to copy that data into memory multiple times.

`.expect("Failed to read line");`
에러처리

`println!("You guessed: {}", guess);`

### rand

Rust에는 랜덤숫자를 뽑아주는 기능이 없지만 rand 라이브러리가 있음

`use rand::Rng;`
The Rng trait defines methods that random number generators implement, and this trait must be in scope for us to use those methods.
Chapter 10 will cover traits in detail.

`cargo doc --open`
which will build documentation provided by all of your dependencies locally and open it in your browser. If you’re interested in other functionality in the rand crate, for example, run cargo doc --open and click rand in the sidebar on the left.
