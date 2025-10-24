# 学习记录笔记

本笔记用于按阶段记录 Python 学习过程中的重要收获、问题与解决方案。欢迎随时补充自己的心得，也可整理值得保留的 Codex CLI 回复。

## 使用说明

- 每次学习后添加日期小节，简介当日主题、遇到的难点与解决方法。
- 将自己的总结放在「自我反思」栏，将助手提供的关键回复或命令放在「助手提示」栏，便于日后查阅。
- 若引用了代码片段，请使用 Markdown 代码块并注明对应文件或命令。

## 模板示例

```markdown
### 2025-01-15：函数式编程练习
- 自我反思：理解 map/filter 的懒加载特性，并尝试重构 `src/tutorials/iterables.py`。
- 助手提示：`python -m pytest tests/iterables/test_lazy_eval.py -k map` 可针对新用例快速回归。
- 下一步：查阅 itertools 文档，编写更多生成器练习。
```

## 待补充

- 今日暂未记录，请在学习结束后按模板添加条目。

## 学习条目

### 2025-10-24：Python REPL 行编辑与 TAB 补全

#### 我的提问

- REPL 内的复制键是不是 `Ctrl-C`？

#### 助手回答（精简记录）

- `Ctrl-C` 在 Python REPL 中用于中断当前输入或执行，按下后会抛出 `KeyboardInterrupt`，不承担复制功能。
- 若要复制或粘贴文本，请使用终端或操作系统提供的快捷键：macOS 使用 `⌘C`/`⌘V`，大多数 Linux 终端使用 `Ctrl-Shift-C`/`Ctrl-Shift-V`。
- `Ctrl-Y` 仅能恢复刚由 `Ctrl-K` 或 `Ctrl-W` 删除的文本，与系统剪贴板无关。

#### 自我反思

- 以后测试快捷键时直接按键验证，不再把组合键当成文字输入，避免出现 `NameError`。

#### 下一步

- 确认 `~/.pythonrc.py` 生效后，在每次进入 REPL 时练习 `Ctrl-K`、`Ctrl-Y` 与系统剪贴板快捷键的结合使用。
