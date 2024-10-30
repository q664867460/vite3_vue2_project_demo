# 提交类型规范

本项目遵守 Conventional Commits 规范中定义的核心类型

## 1. 提交格式

~~~git commont
<类型>[可选范围]: <描述>

[可选正文]

[可选页脚]
~~~



**示例：**

~~~git commont
# 带图标的
:sparkles: feat(button): 新增一个编辑按钮组件
~~~

~~~git commont
# 标准 无图标的
feat(button): 新增一个编辑按钮组件
~~~



## 2. 核心类型

### ✨ feat (Feature 新功能、增强)

**描述：** 引入新功能或增强现有功能。

**模板：**

~~~git commont
# 带图标的
✨ feat(xxx): xxx
:sparkles: feat(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
feat(xxx): xxx
~~~



### 🐛 fix (Bug Fix 修复)

**描述：** 修复错误或缺陷。

~~~git commont
# 带图标的
🐛 fix(xxx): xxx
:bug: fix(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
fix(xxx): xxx
~~~



### 📝 docs (Documentation 文档变更)

**描述：** 仅涉及文档的更改，不涉及代码。

~~~git commont
# 带图标的
📝 docs(xxx): xxx
:memo: docs(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
docs(xxx): xxx
~~~



### 💄 style (Styling 代码格式)

**描述：** 代码格式、缺少分号、空格等非功能性更改，不影响代码的运行。

~~~git commont
# 带图标的
:lipstick: style(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
style(xxx): xxx
~~~



### ♻️ refactor (Code Refactoring 重构)

**描述：** 既不增加feature, 也不是修复bug

~~~git commont
# 带图标的
:recycle: refactor(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
refactor(xxx): xxx
~~~



### ⚡️ perf (Performance Improvement 性能优化)

**描述：** 对代码进行重构，既不是修复错误，也不是添加新功能。

~~~git commont
# 带图标的
:zap: perf(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
perf(xxx): xxx
~~~



### ✅ test (Testing 增加测试)

**描述：** 提升性能的代码更改。

~~~git commont
# 带图标的
:white_check_mark: test(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
test(xxx): xxx
~~~



### 🔧 chore (Chore 构建过程或辅助工具的变动)

**描述：** 其他不修改 src 或 test 文件的杂项任务，如配置文件、脚本等。

~~~git commont
# 带图标的
:wrench: chore(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
chore(xxx): xxx
~~~



### ⏪ revert (Revert 回退)

**描述：** 撤销之前的提交。

~~~git commont
# 带图标的
:rewind: revert(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
revert(xxx): xxx
~~~



### 🚀 build (Build System or External Dependencies 打包)

**描述：** 影响构建系统或外部依赖的更改，例如 Webpack 配置、npm 包更新等。

~~~git commont
# 带图标的
:rocket: build(xxx): xxx
~~~

~~~git commont
# 标准 无图标的
build(xxx): xxx
~~~



## 3. 扩展类型

### 🛡️ security (Security 安全性修复)

**描述：** 修复与安全相关的问题，如漏洞修复、依赖项安全更新等。

**模板：**

~~~git
# 带图标的
:shield: security(xxx): xxx
~~~

~~~git
# 标准 无图标的
security(xxx): xxx
~~~

**示例：**

~~~git
:shield: security(dependencies): 更新 lodash 以修复安全漏洞
~~~

~~~git
security(auth): 增强密码加密算法
~~~



### 🚧 wip (Work In Progress 进行中)

**描述：** 表示正在进行中的工作，尚未完成。通常用于临时提交。

**模板：**

~~~git
# 带图标的
:construction: wip(xxx): xxx
~~~

~~~git
# 标准 无图标的
wip(xxx): xxx
~~~

**示例：**

~~~git
:construction: wip(feature-login): 实现用户登录功能
~~~

~~~git
wip(api): 开发新的数据接口
~~~



### 🗑️ remove (移除功能)

**描述：** 移除现有功能、代码或文件。

**模板：**

~~~git
# 带图标的
:wastebasket: remove(xxx): xxx
~~~

~~~git
# 标准 无图标的
remove(xxx): xxx
~~~

**示例：**

~~~git
:wastebasket: remove(old-auth): 删除过时的认证模块
~~~

~~~git
remove(styles): 移除不再使用的 CSS 文件
~~~



### 🎨 layout (布局调整)

**描述：** 对应用的布局进行调整，不涉及功能性变化。

**模板：**

~~~git
# 带图标的
:art: layout(xxx): xxx
~~~

~~~git
# 标准 无图标的
layout(xxx): xxx
~~~

**示例：**

~~~git
:art: layout(home-page): 优化主页布局
~~~

~~~git
layout(dashboard): 调整仪表盘组件排列
~~~



----



## 4. 破坏性更改

如果一次提交引入了破坏性更改（即对现有功能产生不兼容影响的更改），可以在类型后添加 ! 标记。

**OR**

在提交信息的主体部分明确说明破坏性更改



### 类型后添加 ! 标记

~~~git
feat!: 重构认证系统，API 接口发生变化
~~~



### 明确说明破坏性更改

~~~git
feat(auth): 更改认证流程

BREAKING CHANGE: 这次更改引入了新的认证机制，可能会导致现有客户端无法正常工作。
~~~



---



## 5. 关闭与该提交相关联的问题（Issue）

Closes #xxx 在 Git 提交信息中通常用于自动关闭与该提交相关联的问题（Issue）。

这是基于许多代码托管平台（如 GitHub、GitLab 等）提供的自动化功能。

当你在提交信息或拉取请求（Pull Request）中包含特定的关键词（如 `Closes`、`Fixes`、`Resolves` 等）后跟随问题编号时，这些平台会在合并提交后自动关闭对应的问题。



### 具体解释

- **Closes #456 的含义：**
  - **自动关闭问题：** 当包含 `Closes #456` 的提交被合并到主分支时，编号为 `456` 的问题会被自动标记为已解决并关闭。
  - **关联提交与问题：** 这有助于在代码提交历史中明确指出哪些提交解决了哪些问题，增强项目的可追溯性和透明度。

**使用示例**

假设你在项目中有一个编号为 `456` 的问题，描述为“修复用户登录时的验证错误”。当你完成这个问题的修复并提交代码时，可以这样写提交信息：

~~~git
fix(auth): 修复用户登录时的验证错误

Closes #456
~~~

**效果：**

- 提交代码后，问题 `#456` 会自动关闭，表明该问题已经通过这次提交得到了修复。

### 支持的关键词

不同的平台可能支持不同的关键词来实现自动关闭问题的功能，常见的包括：

- `Closes`
- `Fixes`
- `Resolves`



----



## 6. 参考资料

- [Gitmoji](https://gitmoji.dev/) - 一个使用表情符号来表示 Git 提交类型的标准。
- [Conventional Commits 规范](https://www.conventionalcommits.org/en/v1.0.0/) - 定义了标准化的提交消息格式，旨在提高提交历史的可读性和自动化工具的兼容性。