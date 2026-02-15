# CS61C: Great Ideas in Computer Architecture 💻

这是我在学习 **UC Berkeley CS61C (Spring 2025/2026)** 课程期间完成的实验室练习（Labs）和项目（Projects）代码库。



## 📌 项目简介
CS61C 是关于计算机底层架构的课程，涵盖了从 C 语言编程、汇编语言到 CPU 设计和并行计算的核心概念。

本仓库主要包含以下内容：
* **C 编程基础**：包括指针操作、手动内存管理（`malloc`, `free`）以及自定义数据结构（如动态数组 `vector_t`）。
* **机器级表示**：RISC-V 汇编语言编写与调试。
* **计算机体系结构**：缓存（Cache）优化、流水线（Pipelining）以及逻辑电路设计。

---

## 📂 目录结构

* `lab01/` - C 语言入门与调试（GDB, Valgrind）
* `lab02/` - 链表与内存分配练习
* `projects/proj1/` - 简单的 C 语言应用（例如：SNAKE 贪吃蛇游戏实现）
* `vector_implementation/` - 自定义动态向量容器的实现（包含 `vector_new`, `vector_set`, `vector_get` 等功能）

---

## 🛠️ 工具链与环境
为了编译和运行这些代码，我使用了以下工具：
* **编译器**: `gcc` (支持 C99 标准)
* **调试器**: `GDB`
* **内存检查**: `Valgrind` (用于检测内存泄漏)
* **汇编模拟器**: `Venus` (RISC-V Simulator)

---

## 🚀 核心实现亮点：动态向量 (vector_t)
在学习过程中，我实现了一个可以自动扩容的动态向量，它具备以下特性：
* **自动扩容**：通过 `realloc` 实现，当索引超出当前范围时自动增长。
* **安全性**：包含严格的空指针检查和内存分配失败处理。
* **零初始化**：确保新开辟的内存空间被初始化为 `0`。

```c
// 核心逻辑示例
void vector_set(vector_t *v, size_t loc, int value);
int vector_get(vector_t *v, size_t loc);
