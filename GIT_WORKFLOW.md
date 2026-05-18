# Git工作流程指南

## 📦 版本管理策略

本项目使用Git进行版本管理，采用**功能分支工作流**，适合个人项目和作品集展示。

---

## 🌿 分支策略

### 主要分支

```
main (主分支)
  ├── docs/product-design (产品设计分支)
  ├── feature/backend-core (后端核心功能)
  ├── feature/frontend-ui (前端界面)
  └── feature/ai-engine (AI引擎)
```

### 分支说明

| 分支名 | 用途 | 生命周期 |
|--------|------|---------|
| `main` | 主分支，稳定版本 | 永久 |
| `docs/product-design` | 产品文档开发 | Day 1-9 |
| `feature/backend-core` | 后端核心功能 | Day 10-12 |
| `feature/frontend-ui` | 前端界面开发 | Day 13-14 |
| `feature/ai-engine` | AI引擎开发 | Day 11 |
| `feature/deployment` | 部署配置 | Day 16 |

---

## 🚀 初始化Git仓库

### 1. 本地初始化

```bash
# 进入项目目录
cd D:\work\code\TourismAgent

# 初始化Git仓库
git init

# 添加所有文件
git add .

# 首次提交
git commit -m "Initial commit: Project setup with documentation"
```

### 2. 创建GitHub仓库

1. 访问 https://github.com/new
2. 仓库名：`TourismAgent` 或 `ai-travel-assistant`
3. 描述：`AI-powered travel planning platform with community guides - Product Manager Portfolio Project`
4. 选择 **Public**（作品集展示）
5. **不要**勾选 "Add README" 等选项（我们已经有了）
6. 点击 "Create repository"

### 3. 关联远程仓库

```bash
# 添加远程仓库（替换YOUR_USERNAME为你的GitHub用户名）
git remote add origin https://github.com/YOUR_USERNAME/TourismAgent.git

# 推送到远程
git branch -M main
git push -u origin main
```

---

## 📝 提交规范

### Commit Message格式

采用 **Conventional Commits** 规范：

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Type类型

| Type | 说明 | 示例 |
|------|------|------|
| `docs` | 产品文档 | `docs(market): Add market analysis document` |
| `feat` | 新功能 | `feat(auth): Add user registration API` |
| `fix` | Bug修复 | `fix(itinerary): Fix AI generation timeout` |
| `refactor` | 重构 | `refactor(api): Restructure guide endpoints` |
| `style` | 样式调整 | `style(ui): Update homepage layout` |
| `test` | 测试 | `test(auth): Add login API tests` |
| `chore` | 构建/工具 | `chore: Update dependencies` |

### 示例

```bash
# 产品文档提交
git commit -m "docs(competitive): Complete competitive analysis for travel platforms"

# 功能开发提交
git commit -m "feat(ai-engine): Implement rule-based itinerary generator

- Add city templates for Beijing, Shanghai, Chengdu
- Implement routing logic between rule engine and LLM
- Add attraction seed data"

# Bug修复提交
git commit -m "fix(auth): Resolve JWT token expiration issue"
```

---

## 🔄 日常工作流程

### Day 1-9: 产品设计阶段

```bash
# 创建产品设计分支
git checkout -b docs/product-design

# 每完成一份文档就提交
git add docs/market_analysis.md
git commit -m "docs(market): Complete market analysis document"

git add docs/competitive_analysis.md
git commit -m "docs(competitive): Add competitive analysis for 5 major platforms"

# ... 继续其他文档

# 完成后合并到main
git checkout main
git merge docs/product-design
git push origin main

# 可选：推送分支到远程（保留历史）
git push origin docs/product-design
```

### Day 10-16: 开发阶段

```bash
# 后端开发
git checkout -b feature/backend-core

# 完成用户系统
git add backend/app/models/user.py backend/app/api/auth.py
git commit -m "feat(auth): Implement user registration and login

- Add User model with password hashing
- Implement JWT-based authentication
- Add registration and login endpoints"

# 完成AI引擎
git checkout -b feature/ai-engine
git add backend/app/services/ai_engine/
git commit -m "feat(ai): Implement hybrid AI itinerary generator

- Add rule engine with city templates
- Integrate Claude API for complex requests
- Implement routing logic"

# 合并到main
git checkout main
git merge feature/backend-core
git merge feature/ai-engine
git push origin main
```

### 前端开发

```bash
# 前端开发
git checkout -b feature/frontend-ui

# 完成核心页面
git add frontend/src/views/
git commit -m "feat(ui): Add core pages for itinerary and guides

- Implement ItineraryGenerator page with form
- Add GuideList and GuideDetail pages
- Create reusable components"

# 合并到main
git checkout main
git merge feature/frontend-ui
git push origin main
```

---

## 🏷️ 版本标签

在关键里程碑打标签：

```bash
# 产品设计完成
git tag -a v0.1.0 -m "Product design phase completed"
git push origin v0.1.0

# MVP开发完成
git tag -a v0.2.0 -m "MVP development completed"
git push origin v0.2.0

# 部署上线
git tag -a v1.0.0 -m "First production release"
git push origin v1.0.0
```

---

## 📊 提交历史建议

### 理想的提交历史

```
* v1.0.0 - First production release (Day 21)
* docs(retrospective): Add product retrospective document (Day 19)
* docs(iteration): Add V2 iteration plan (Day 18)
* feat(deploy): Add Docker configuration and deployment docs (Day 16)
* test: Add comprehensive API tests (Day 15)
* feat(ui): Complete all frontend pages (Day 14)
* feat(ui): Add core pages for itinerary and guides (Day 13)
* feat(community): Implement guide CRUD and interaction APIs (Day 12)
* feat(ai): Implement hybrid AI itinerary generator (Day 11)
* feat(auth): Implement user registration and login (Day 10)
* v0.1.0 - Product design phase completed (Day 9)
* docs(technical): Add technical specification document (Day 9)
* docs(data): Add data strategy and metrics definition (Day 8)
* docs(wireframes): Add interaction design and wireframes (Day 7)
* docs(ia): Add information architecture document (Day 6)
* docs(prd): Complete product requirements document (Day 5)
* docs(requirements): Add requirements definition with prioritization (Day 4)
* docs(user): Complete user research and personas (Day 3)
* docs(competitive): Add competitive analysis (Day 2)
* docs(market): Complete market analysis document (Day 1)
* Initial commit: Project setup with documentation
```

---

## 🔍 查看历史

```bash
# 查看提交历史
git log --oneline --graph --all

# 查看某个文件的修改历史
git log --follow docs/PRD.md

# 查看某次提交的详细内容
git show <commit-hash>

# 查看分支图
git log --graph --oneline --all --decorate
```

---

## 🛡️ 最佳实践

### 1. 频繁提交
- 每完成一个小功能就提交
- 每份文档完成就提交
- 不要积累太多改动

### 2. 有意义的提交信息
- 说明"做了什么"和"为什么"
- 使用规范的格式
- 避免"update"、"fix bug"等模糊描述

### 3. 保持main分支稳定
- 不要直接在main上开发
- 功能完成并测试后再合并
- 合并前确保代码可运行

### 4. 使用分支
- 产品文档用 `docs/` 前缀
- 功能开发用 `feature/` 前缀
- Bug修复用 `fix/` 前缀

### 5. 定期推送
```bash
# 每天结束时推送
git push origin main
git push origin <current-branch>
```

---

## 📦 .gitignore说明

已创建 `.gitignore` 文件，排除：
- 依赖目录（node_modules, venv）
- 环境变量文件（.env）
- 数据库文件（*.db）
- 构建产物（dist, build）
- IDE配置（.vscode, .idea）
- 上传文件（uploads/）

---

## 🎯 作品集展示建议

### README徽章

在README.md顶部添加徽章：

```markdown
![GitHub last commit](https://img.shields.io/github/last-commit/YOUR_USERNAME/TourismAgent)
![GitHub repo size](https://img.shields.io/github/repo-size/YOUR_USERNAME/TourismAgent)
![GitHub language count](https://img.shields.io/github/languages/count/YOUR_USERNAME/TourismAgent)
```

### 项目描述

在GitHub仓库设置中添加：
- **Description**: `AI-powered travel planning platform - Product Manager Portfolio Project`
- **Website**: 部署后的线上地址
- **Topics**: `product-management`, `ai`, `travel`, `vue`, `flask`, `portfolio`

### 固定重要文档

在README中添加"文档导航"部分，链接到关键文档。

---

## 🚨 常见问题

### Q1: 忘记切换分支直接在main上改了怎么办？
```bash
# 创建新分支保存当前改动
git checkout -b feature/my-feature

# 提交改动
git add .
git commit -m "feat: Add feature"

# 切回main并合并
git checkout main
git merge feature/my-feature
```

### Q2: 提交信息写错了怎么办？
```bash
# 修改最后一次提交信息（未push）
git commit --amend -m "New commit message"

# 如果已经push，不建议修改
```

### Q3: 想撤销某个文件的修改？
```bash
# 撤销未暂存的修改
git checkout -- <file>

# 撤销已暂存的修改
git reset HEAD <file>
git checkout -- <file>
```

---

## 📅 推荐的Git工作节奏

### 每日结束
```bash
git add .
git commit -m "docs/feat: Daily progress summary"
git push origin main
```

### 每个阶段完成
```bash
git tag -a v0.x.0 -m "Phase X completed"
git push origin v0.x.0
```

### 项目完成
```bash
git tag -a v1.0.0 -m "Project completed"
git push origin v1.0.0
```

---

## 🎓 学习资源

- [Git官方文档](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Conventional Commits](https://www.conventionalcommits.org/)

---

**现在可以开始初始化Git仓库了！** 🚀