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
