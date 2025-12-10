# Contributing to YuanYu

欢迎为原语言项目做出贡献！

## Git Commit 规范

我们采用 [Conventional Commits](https://www.conventionalcommits.org/) 规范。

### 格式

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Type（必需）

| Type | 说明 | 示例 |
|------|------|------|
| `feat` | 新功能 | `feat(core): add time primitives` |
| `fix` | 修复问题 | `fix(templates): correct YAML schema` |
| `docs` | 文档变更 | `docs: update GUIDE with new examples` |
| `style` | 格式调整（不影响功能） | `style(examples): format accounting.yaml` |
| `refactor` | 代码重组（不改功能） | `refactor(domains): restructure game package` |
| `perf` | 性能优化 | `perf(primitives): optimize lookup performance` |
| `test` | 测试相关 | `test: add validation for YAML syntax` |
| `chore` | 构建、工具、依赖 | `chore: initialize git repository` |

### Scope（可选）

选择与变更相关的作用域：

- `core` — 核心原语定义 (`core/primitives.yaml`)
- `domains` — 领域包 (`domains/tv/`, `domains/game/`)
- `examples` — 使用示例 (`examples/`)
- `prompts` — AI 提示词 (`prompts/`)
- `templates` — 项目模板 (`templates/`)
- `docs` — 文档 (`README.md`, `SPEC.md`, `GUIDE.md`)
- `config` — 配置和工具

### Subject（必需）

- 使用**英文**，祈使语气，现在时
- 第一个字母**小写**
- **不要**以句点结尾
- 最多 **50 字符**
- 清晰准确地描述变更内容

✅ 好的例子：
```
add 4 relationship primitives (bind, unbind, parent, dependency)
update SPEC with relationship layer examples
fix YAML syntax in accounting-pet example
```

❌ 不好的例子：
```
原语言 v0.1 - 月影工坊出品        # 太长且不专业
Add new features                  # 首字母大写
Fixed bug in template.           # 句点结尾
```

### Body（可选）

用来说明**为什么**做这个变更，而不是**怎么**做。

- 每行最多 72 字符
- 与 subject 之间空一行
- 用 `#` 标题组织复杂内容

示例：
```
feat(core): add quantity primitives

新增 4 个数量相关的原语，用于描述系统中数量的增减和限制。

原语：
- count: 计数
- increment/decrement: 增减
- upper/lower limit: 上下限

这些原语补充了存在类和数据类，完善了原语体系。
```

### Footer（可选）

- 引用相关 Issue: `Closes #123`, `Related to #456`
- Breaking Change: `BREAKING CHANGE: description`

示例：
```
BREAKING CHANGE: renamed "信息" layer to "data" for internationalization
Closes #42
```

---

## 工作流

1. **创建分支**
   ```bash
   git checkout -b feat/descriptive-name
   git checkout -b fix/issue-number
   ```

2. **提交变更**
   ```bash
   git add <files>
   git commit  # 使用 .gitmessage 模板
   ```

3. **推送并提交 PR**
   ```bash
   git push origin feat/descriptive-name
   ```

4. **保持代码整洁**
   - 确保没有多余的空白行
   - YAML 缩进 2 个空格
   - Markdown 行宽 80-100 字符

---

## 文件结构规范

```
yuanyu/
├── core/
│   └── primitives.yaml      # 48 个原语定义
├── domains/
│   ├── tv/
│   │   └── index.yaml       # TV 领域特定原语
│   └── game/
│       └── index.yaml       # 游戏领域特定原语
├── examples/
│   ├── accounting.yaml      # 简单示例
│   └── accounting-pet.yaml  # 组合示例
├── prompts/
│   └── system-prompt.md     # AI 系统提示词
├── templates/
│   └── basic.yaml           # 基础模板
├── README.md                # 项目首页
├── SPEC.md                  # 规范文档
├── GUIDE.md                 # 使用指南
├── CONTRIBUTING.md          # 本文件
├── .gitmessage              # Commit 消息模板
└── LICENSE                  # Apache 2.0 许可证
```

---

## 常见场景的 Commit Message

### 添加新原语
```
feat(core): add existence primitives (create, destroy, copy, reference)
```

### 添加新领域包
```
feat(domains): add game domain package with growth, reward, resource, social primitives
```

### 添加使用示例
```
feat(examples): add stacked combination example (accounting-pet)
```

### 更新文档
```
docs: update README with documentation roadmap
docs(guide): add advanced usage section with domain packages
```

### 修复 YAML 语法
```
fix(examples): correct indentation in accounting.yaml
```

### 重组代码结构
```
refactor(domains): organize TV package with separate concerns
```

### 更新许可证
```
chore(license): add Apache 2.0 with company attribution
```

---

## 提交前检查清单

- [ ] Commit message 符合规范
- [ ] YAML 文件格式正确（可用在线验证器检查）
- [ ] 文档链接有效
- [ ] 没有添加多余的空白或注释

---

感谢您的贡献！

**月影工坊** — 伴月之星网络科技
