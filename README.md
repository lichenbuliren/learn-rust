# Rust 笔记

# 基础概念

- 外部包：`crate`
- Cargo.toml 与 Cargo.lock：类似于 package.json 与 package-lock.json

## 编译构建

``` bash
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