# 学习进度记录

## 2025-10-24：Python REPL Tab 补全
- 环境准备：安装 `gnureadline` 并在 `~/.pythonrc.py` 中优先导入，绑定 `tab: complete`、`set show-all-if-ambiguous on`，确保 GNU Readline 补全生效。
- 验证步骤：在 REPL 中执行 `import os`，输入 `os.pa` 后按 `Tab`，阅读列出的候选项（`os.path`、`os.pardir` 等），随后输入更多字符使其唯一并成功补全。
- 经验笔记：按下 `Tab` 后若仅出现列表而非自动补齐，需继续输入以缩小候选；若见不到候选，确认是否处于交互 REPL 且 `PYTHONSTARTUP` 生效。
- 待学习：继续进行 Tab 补全测试第二关，探索对象属性补全与候选列表的操作技巧。

## 2025-10-24：Tab 补全第二关（datetime 对象）
- 操作过程：`from datetime import datetime` → `now = datetime.now()`，输入 `now.` 后双击 `Tab` 查看属性列表（`isoformat`, `strftime`, `dst`, …）。
- 补全练习：尝试 `now.iso<Tab>` 补成 `now.isoformat()` 并执行；使用 `now.st<Tab>` 时看到提示“Did you mean: dst?”，说明需给出更精确前缀。
- 陷阱记录：直接输入 `now.iso` 或 `now.st` 回车会抛出 `AttributeError`，Tab 补全需要在属性名后补上括号或继续补前缀。
- 下一步：继续第三关，针对自定义对象与 `__getattr__` 的补全行为进行实验。

## 2025-10-24：Tab 补全第三关（自定义类）
- 定义 `Greeter` 类时，由于漏写空行直接在交互提示符内输入 `g = Greeter()`，导致缩进上下文未结束而触发 `SyntaxError: invalid syntax`。
- 修正方法：在交互定义类时按两次回车结束类体，再重新键入 `g = Greeter()`。
- 下一步：重新执行补全实验（`g.he<Tab>`）并验证补全结果，以及测试带 `__getattr__` 的动态属性行为。
