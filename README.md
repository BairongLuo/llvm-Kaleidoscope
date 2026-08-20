# llvm-Kaleidoscope

跟随 [LLVM 官方教程](https://llvm.org/docs/tutorial/MyFirstLanguageFrontend/) 实现的 Kaleidoscope 语言 toy compiler，使用 C++ 与 LLVM IR。

## 当前进度

- [x] Ch1 词法分析（Lexer）
- [x] Ch2 语法分析（递归下降 Parser）
- [x] Ch3 AST 与 LLVM IR 代码生成
- [ ] Ch4 JIT 即时编译
- [ ] Ch5 控制流（if/for）
- [ ] Ch6 用户自定义运算符
- [ ] Ch7 可变变量
- [ ] Ch9 调试信息

## 构建

依赖：LLVM 16 及以上版本、clang++。

```bash
# Ubuntu / Debian 安装依赖
sudo apt install llvm clang

# 编译
clang++ -g -O3 toy.cpp $(llvm-config --cxxflags --ldflags --system-libs --libs core) -o toy
```

## 运行

```bash
./toy
ready> def foo(x) x * 2;
ready> foo(21);
```

输入表达式或函数定义后，程序会打印生成的 LLVM IR；按 `Ctrl-D` 退出。

## 后续计划

- 将代码生成迁移到 ORC JIT 接口
- 为语言扩展新特性（如字符串、数组）
- 编写自定义 LLVM Pass，练习程序分析
