# Rust 笔记

# 基础概念

- 外部包：`crate`
- Cargo.toml 与 Cargo.lock：类似于 package.json 与 package-lock.json

## 基础语法

### 变量声明

```rust
let foo = bar; // 变量不可变
let mut bar = 5;; // 变量可变
```

## println

```rust
let x = 5;
let y = 10;
// {} 为占位符
println!("x = {}, y = {}", x, y);
```

## 语言特性

**Rust 允许一个新值来隐藏之前值**

```rust
let mut guess = String::new();

io::stdin().read_line(&mut guess)
    .expect("Failed to read line");

let guess: u32 = guess.trim().parse()
    .expect("Please type a number!");
```

**数字类型**

> Rust 的默认类型通常就很好，数字类型默认是 i32：它通常是最快的，甚至在 64 位系统上也是

**包含语句和表达式的函数体**

> 语句（Statements）是执行一些操作但不返回值的指令。表达式（Expressions）计算并产生一个值;
> 表达式的结尾没有分号。如果在表达式的结尾加上分号，它就变成了语句，而语句不会返回值。在接下来探索具有返回值的函数和表达式时要谨记这一点

```rust
fn main() {
    let x = 5;

    let y = {
        let x = 3;
        x + 1
    };

    println!("The value of y is: {}", y);
}
```

**具有返回值的函数**

> 函数可以向调用它的代码返回值。我们并不对返回值命名，但要在箭头（->）后声明它的类型。在 Rust 中，函数的返回值等同于函数体最后一个表达式的值。使用 return 关键字和指定值，可从函数中提前返回；但大部分函数隐式的返回最后的表达式。

```rust
fn five() -> i32 {
    5
}

fn main() {
    let x = five();

    println!("The value of x is: {}", x);
}
```

### 基础库

```rust
use std::io; // io 标准库，输入/输出
use std::cmp::Ordering; // 逻辑判断大小
```

## 编译构建

```bash
# 构建
cargo build

# 构建 + 运行
cargo run

# 检查是否可编译，但是不生成可执行文件
cargo check
```

## 构建产物

- 调试阶段：`target/debug/`
- 发布构建：`target/release/`

## VScode 问题

### 手动配置 rustup 本地路径

在 vscode 配置中，新增一个 rust 本地路径

```json
{
  "rust-client.rustupPath": "/Users/weirufeng/.cargo/bin/rustup"
}
```
