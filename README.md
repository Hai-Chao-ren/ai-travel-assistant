# TourismAgent - AI智能旅行助手 + 攻略社区

> 一个以产品经理视角完整实践的旅游互联网产品项目
> 
> **目标岗位**：AI产品经理 / 互联网旅游产品经理实习

---

## 📋 项目概述

### 产品定位
AI行程规划 + 攻略社区结合的旅游平台，为年轻旅行者提供智能行程生成和社区化旅游攻略分享。

### 核心价值
- **用户价值**：输入偏好即可获得个性化行程方案，同时浏览真实用户分享的旅游攻略
- **差异化**：AI混合引擎（规则引擎+大模型）+ 攻略社区双轮驱动
- **目标用户**：18-35岁年轻旅行者，追求个性化和高效规划

### 项目目标
1. **系统训练产品思维和PM方法论**
2. **产出高质量的产品文档体系作为作品集**
3. **附带可运行Demo验证产品设计**

---

## 🎯 核心功能（MVP）

### 1. AI行程生成
- 用户输入目的地、天数、偏好
- AI生成多日行程（景点、美食、交通、住宿）
- 支持保存和收藏行程

### 2. 攻略社区
- 用户发布图文游记/攻略
- 浏览、搜索攻略
- 点赞、评论、收藏

### 3. 用户系统
- 注册登录
- 个人主页
- 收藏管理

### 4. 个性化推荐
- 基于用户历史和偏好推荐目的地
- 推荐相关攻略

---

## 🏗️ 技术架构

### 技术栈

- **后端**：Python Flask + SQLAlchemy + Flask-JWT
- **前端**：Vue 3 + Vite + Tailwind CSS + Pinia
- **数据库**：SQLite (MVP) → PostgreSQL (生产)
- **AI能力**：Claude API (Anthropic)
- **部署**：Docker + Railway/Render

### 架构图

```
┌─────────────────────────────────────────┐
│   Frontend (Vue 3 + Tailwind CSS)      │
│   - 用户界面                             │
│   - 状态管理 (Pinia)                     │
└──────────────┬──────────────────────────┘
               │ REST API
┌──────────────▼──────────────────────────┐
│   Backend (Flask)                       │
│   ┌─────────────────────────────────┐   │
│   │ API Layer                       │   │
│   │ - auth, guides, itinerary       │   │
│   └─────────────┬───────────────────┘   │
│   ┌─────────────▼───────────────────┐   │
│   │ Service Layer                   │   │
│   │ - AI Engine (混合方案)           │   │
│   │ - Recommendation                │   │
│   └─────────────┬───────────────────┘   │
│   ┌─────────────▼───────────────────┐   │
│   │ Data Layer (SQLAlchemy ORM)    │   │
│   └─────────────┬───────────────────┘   │
└─────────────────┼───────────────────────┘
                  │
    ┌─────────────┴─────────────┐
    │                           │
┌───▼────┐              ┌───────▼────┐
│ SQLite │              │ Claude API │
│  数据库 │              │  AI生成    │
└────────┘              └────────────┘
```

### AI混合引擎设计

```
用户输入 → 路由决策器
              │
    ┌─────────┴─────────┐
    │                   │
┌───▼────┐      ┌───────▼────┐
│规则引擎│      │  LLM API   │
│热门城市│      │  复杂需求  │
│标准行程│      │  智能生成  │
└───┬────┘      └───────┬────┘
    │                   │
    └─────────┬─────────┘
              │
         统一JSON输出
```

**路由策略**：
- 热门城市 + 标准天数 → 规则引擎（快速、免费）
- 复杂需求 + 特殊偏好 → Claude API（智能、灵活）

---

## 📅 项目时间线（3周）

### 第一周：产品设计（Day 1-9）— 核心产出阶段

| Day | 阶段 | 产出文档 |
|-----|------|---------|
| 1 | 市场分析 | `docs/market_analysis.md` |
| 2 | 竞品分析 | `docs/competitive_analysis.md` |
| 3 | 用户研究 | `docs/user_research.md` |
| 4 | 需求定义 | `docs/requirements.md` |
| 5 | 产品PRD | `docs/PRD.md` |
| 6 | 信息架构 | `docs/information_architecture.md` |
| 7 | 交互设计 | `docs/wireframes.md` |
| 8 | 数据策略 | `docs/data_strategy.md` |
| 9 | 技术方案 | `docs/technical_spec.md` |

### 第二周：开发实现（Day 10-16）— AI辅助快速完成

| Day | 任务 |
|-----|------|
| 10 | 项目初始化 + 数据库 + 用户系统 |
| 11 | AI行程生成（规则引擎 + LLM集成） |
| 12 | 攻略社区后端（CRUD + 互动） |
| 13 | 前端搭建 + 核心页面 |
| 14 | 前端剩余页面 + 联调 |
| 15 | Bug修复 + 测试 |
| 16 | Docker化 + 部署上线 |

### 第三周：迭代与总结（Day 17-21）

| Day | 任务 |
|-----|------|
| 17 | 数据观察、用户反馈收集（模拟） |
| 18 | 迭代规划文档 |
| 19 | 产品复盘文档 |
| 20 | Portfolio整理 |
| 21 | 演示准备 |

---

## 📚 产品文档体系

### 文档列表与PM思维训练

| 文档 | PM能力训练 | 核心问题 |
|------|-----------|---------|
| 市场分析 | "看大局" | 为什么是现在？为什么是这个方向？ |
| 竞品分析 | "拆解产品" | 别人做了什么？没做什么？为什么？ |
| 用户研究 | "共情用户" | 用户真正要的是什么？ |
| 需求定义 | "取舍决策" | 做什么比怎么做更重要 |
| PRD | "精确表达" | 写到开发不需要问就能做 |
| 信息架构 | "结构化思维" | 用户怎么找到想要的？ |
| 交互设计 | "体验设计" | 每一步用户会怎么想？ |
| 数据策略 | "数据驱动" | 怎么知道做对了？ |
| 技术方案 | "跨职能沟通" | 怎么和开发对齐？ |

---

## 🗂️ 项目目录结构

```
TourismAgent/
├── docs/                        # 产品文档体系（作品集核心）
│   ├── market_analysis.md
│   ├── competitive_analysis.md
│   ├── user_research.md
│   ├── requirements.md
│   ├── PRD.md
│   ├── information_architecture.md
│   ├── wireframes.md
│   ├── data_strategy.md
│   ├── technical_spec.md
│   ├── iteration_plan.md
│   └── retrospective.md
├── backend/
│   ├── app/
│   │   ├── __init__.py
│   │   ├── config.py
│   │   ├── extensions.py
│   │   ├── models/              # 数据模型
│   │   │   ├── user.py
│   │   │   ├── guide.py
│   │   │   ├── itinerary.py
│   │   │   └── ...
│   │   ├── api/                 # API端点
│   │   │   ├── auth.py
│   │   │   ├── guides.py
│   │   │   ├── itinerary.py
│   │   │   └── ...
│   │   ├── services/
│   │   │   └── ai_engine/       # AI混合引擎
│   │   │       ├── router.py
│   │   │       ├── rule_engine.py
│   │   │       ├── llm_service.py
│   │   │       └── prompts.py
│   │   ├── utils/
│   │   └── data/                # 种子数据
│   ├── tests/
│   ├── requirements.txt
│   ├── Dockerfile
│   └── run.py
├── frontend/
│   ├── src/
│   │   ├── views/               # 页面组件
│   │   ├── components/          # 通用组件
│   │   ├── stores/              # 状态管理
│   │   ├── api/                 # API封装
│   │   └── router/
│   ├── package.json
│   └── vite.config.js
├── docker-compose.yml
├── CLAUDE.md                    # AI辅助规范
└── README.md
```

---

## 🎨 核心页面

1. **首页** - 推荐目的地 + 热门攻略 + AI生成入口
2. **AI行程生成页** - 表单输入 + 结果展示
3. **攻略列表页** - 卡片流 + 筛选搜索
4. **攻略详情页** - 图文内容 + 评论互动
5. **攻略发布页** - 富文本编辑器 + 图片上传
6. **用户中心** - 个人信息 + 我的行程 + 我的攻略 + 收藏

---

## 🗄️ 数据库设计

### 核心表

- `users` - 用户信息 + 旅行偏好
- `guides` - 攻略（标题/目的地/内容/标签/互动数据）
- `itineraries` - AI生成行程
- `attractions` - 景点POI数据（规则引擎用）
- `comments` - 评论
- `likes` - 点赞
- `favorites` - 收藏

---

## 🚀 快速开始

### 环境要求

- Python 3.9+
- Node.js 18+
- Claude API Key

### 后端启动

```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env  # 配置环境变量
flask db upgrade
python run.py
```

### 前端启动

```bash
cd frontend
npm install
npm run dev
```

### Docker启动

```bash
docker-compose up -d
```

---

## ✅ 验证标准

1. **产品文档** - 逻辑自洽、专业度高、可展示
2. **Demo功能** - 核心流程可跑通
3. **部署上线** - 线上可访问
4. **Portfolio** - README清晰展示项目全貌

---

## 📖 学习资源

### PM方法论
- KANO模型 - 需求分类
- ICE评分 - 优先级排序
- 用户旅程地图 - 体验设计
- 北极星指标 - 数据驱动

### 技术文档
- Flask官方文档
- Vue 3官方文档
- Claude API文档

---

## 👤 作者

产品经理实习作品集项目

---

## 📄 License

MIT
