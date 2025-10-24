# pylearn

个人 Python 学习资料与示例的集中仓库。用于整理教程、随堂笔记、示例代码与配套工具，便于持续迭代与复盘。

## 仓库结构

- `src/`：可复用的教学示例与工具模块。
- `tests/`：与源代码一一对应的测试用例。
- `notebooks/`：学习过程中的笔记与实验脚本（文件名包含日期与主题）。
- `resources/`：公共数据、样例输入及静态资源。
- `AGENTS.md`、`LEARNING_NOTES.md`、`LEARNING_PROGRESS.md`：学习记录与知识点总结。

## 快速开始

```bash
python -m venv .venv
source .venv/bin/activate  # Windows 使用 .venv\Scripts\activate
pip install -r requirements.txt
```

## 开发与测试

- 代码格式：`black src tests`
- 静态检查：`ruff check src tests`
- 全量测试：`python -m pytest`
- 冒烟测试：`python -m pytest tests/unit --maxfail=1 -q`
- 覆盖率：`python -m coverage run -m pytest && python -m coverage html`

请确保新增模块补充单元测试，测试覆盖率不低于 90%，修复缺陷时同时提交回归测试。

## 提交流程

1. 以单一主题组织提交，并使用 Conventional Commits，例如：`feat(parser): 支持自定义分隔符`。
2. 提交前运行格式化、静态检查与测试。
3. PR 包含变更摘要、测试结果和必要的截图或日志。
