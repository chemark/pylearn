# Repository Guidelines

本仓库主要用于整理 Python 学习示例与配套工具。请依据以下指引协同开发，确保文档、代码与测试保持一致与可追踪。

## 项目结构与模块组织
- 建议主体代码放在 `src/`，按功能创建子包，例如 `src/tutorials/basics.py`。
- 练习脚本或笔记统一置于 `notebooks/`，文件名应包含日期与主题，便于追溯。
- 公共数据、样例输入及静态资源集中在 `resources/`，避免散落于根目录。
- 为每个源模块在 `tests/` 下创建对应测试文件，如 `tests/tutorials/test_basics.py`，保持一一映射。

## 构建、测试与开发命令
- `python -m venv .venv && source .venv/bin/activate`：创建并启用虚拟环境。
- `pip install -r requirements.txt`：安装运行与开发依赖。
- `python -m pytest`：执行完整测试套件，提交前务必通过。
- `python -m pytest tests/unit --maxfail=1 -q`：快速冒烟测试，适合开发迭代。
- `python -m coverage run -m pytest && python -m coverage html`：生成覆盖率报告，检查薄弱区域。

## 编码风格与命名约定
- 统一遵循 PEP 8，使用四空格缩进；提交前运行 `black src tests` 自动格式化。
- 使用 `ruff check src tests` 进行静态检查，对必须忽略的告警添加原因注释。
- 函数与变量采用 snake_case，类名使用 PascalCase，模块名保持小写并避免空格或特殊符号。
- 鼓励加入类型标注与早返回逻辑，提升代码可读性与测试友好度。

## 测试准则
- 采用 `pytest` 框架，测试目录结构与源代码保持相同层级。
- 测试函数命名描述行为，例如 `test_handles_empty_input`，避免含糊不清。
- 目标分支覆盖率不低于 90%；修复缺陷时必须补充回归测试。
- 若在笔记本中开发，请将可复用逻辑提炼到 `src/`，并对新模块补充单元测试。

## 提交与拉取请求规范
- 使用 Conventional Commits 风格的前缀（如 `feat:`、`fix:`、`test:`），范围信息以括号注明模块，如 `feat(parser): 支持自定义分隔符`。
- 单次提交聚焦单一主题，避免在同一提交混合重构与功能变更。
- 创建 PR 时附上变更摘要、测试结果勾选列表及相关 Issue 链接；涉及可视化输出时提供截图或日志。
- 确认本地测试与 CI 均通过后请求评审，对审查意见及时响应，并记录延后处理的事项。
