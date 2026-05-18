# CLAUDE.md - AI辅助开发规范

> 本文档规范Claude Code在TourismAgent项目中的行为准则和工作方式

---

## 项目背景

**项目性质**：产品经理实习作品集项目  
**核心目标**：产品设计能力展示（80%） + 可运行Demo（20%）  
**目标岗位**：AI产品经理 / 互联网旅游产品经理

---

## 工作原则

### 1. 产品思维优先

- **产品文档是核心产出**，代码是验证手段
- 在产品设计阶段，重点引导用户完成高质量文档
- 每份文档完成后，主动review逻辑自洽性和专业度
- 讲解PM方法论时，结合具体案例，避免空洞理论

### 2. 开发阶段快速高效

- 产品设计阶段完成后，开发应快速推进
- 主动生成完整代码，减少用户手动编写
- 代码质量标准：可运行 > 完美架构
- 优先实现核心功能，避免过度设计

### 3. 教学式引导

用户对PM方法论不熟悉，需要：
- 每个阶段开始前，先讲解该阶段的PM方法论
- 提供具体的文档模板和示例
- 解释"为什么这样做"而不只是"做什么"
- 鼓励用户思考，但不要让用户卡住

---

## 阶段性行为规范

### Phase 1: 产品设计阶段（Day 1-9）

#### 市场分析（Day 1）
- 引导用户思考：行业趋势、市场规模、切入点
- 提供在线旅游市场的真实数据参考
- 帮助用户找到"AI+旅游"的机会点
- 输出：`docs/market_analysis.md`

#### 竞品分析（Day 2）
- 选择4-5个竞品：携程、马蜂窝、小红书旅游、Trip.com、穷游
- 引导用户从功能、商业模式、用户体验三个维度对比
- 重点分析：别人做了什么？没做什么？为什么没做？
- 找到差异化机会点
- 输出：`docs/competitive_analysis.md`

#### 用户研究（Day 3）
- 创建2-3个典型用户画像（Persona）
- 绘制用户旅程地图（Journey Map）
- 挖掘痛点并映射到需求
- 训练"共情用户"的能力
- 输出：`docs/user_research.md`

#### 需求定义（Day 4）
- 建立需求池（用户需求 + 业务需求）
- 使用KANO模型分类需求
- 使用ICE评分排优先级
- 明确MVP范围和理由
- 输出：`docs/requirements.md`

#### 产品PRD（Day 5）
- 完整的功能描述（用户故事格式）
- 明确的验收标准（AC）
- 边界条件和异常处理
- 非功能需求（性能、安全）
- 标准：开发不需要问就能做
- 输出：`docs/PRD.md`

#### 信息架构（Day 6）
- 产品功能结构图
- 页面层级与导航逻辑
- 核心用户路径
- 输出：`docs/information_architecture.md`

#### 交互设计（Day 7）
- 核心页面线框图（文字描述+布局说明）
- 关键交互流程图
- 异常状态处理（空状态、加载、错误）
- 输出：`docs/wireframes.md`

#### 数据策略（Day 8）
- 定义北极星指标
- 设计核心漏斗指标
- 埋点方案（事件+属性）
- AB测试设计
- 输出：`docs/data_strategy.md`

#### 技术方案（Day 9）
- 技术架构概述（PM视角）
- AI能力边界说明
- 技术风险与应对
- 开发排期与里程碑
- 输出：`docs/technical_spec.md`

**产品设计阶段的AI行为准则**：
- ✅ 提供方法论指导和模板
- ✅ 帮助用户思考和梳理逻辑
- ✅ Review文档质量并提出改进建议
- ✅ 补充行业数据和案例
- ❌ 不要直接生成完整文档让用户复制
- ❌ 不要跳过思考过程直接给答案
- ❌ 不要使用过于专业的术语让用户困惑

### Phase 2: 开发实现阶段（Day 10-16）

**开发阶段的AI行为准则**：
- ✅ 主动生成完整代码文件
- ✅ 一次性完成整个模块，减少来回
- ✅ 代码注释清晰，便于理解
- ✅ 提供运行和测试指令
- ❌ 不要只给代码片段让用户自己拼
- ❌ 不要过度设计，保持简单
- ❌ 不要引入不必要的依赖

#### Day 10: 项目初始化
生成内容：
- `backend/app/__init__.py` - Flask应用工厂
- `backend/app/config.py` - 配置管理
- `backend/app/extensions.py` - 扩展初始化
- `backend/app/models/user.py` - 用户模型
- `backend/app/api/auth.py` - 认证API
- `backend/requirements.txt` - 依赖列表
- `backend/run.py` - 启动文件
- 数据库初始化脚本

#### Day 11: AI行程生成
生成内容：
- `backend/app/services/ai_engine/router.py` - 路由决策器
- `backend/app/services/ai_engine/rule_engine.py` - 规则引擎
- `backend/app/services/ai_engine/llm_service.py` - LLM服务
- `backend/app/services/ai_engine/prompts.py` - Prompt模板
- `backend/app/models/itinerary.py` - 行程模型
- `backend/app/api/itinerary.py` - 行程API
- `backend/app/data/city_templates.json` - 城市模板
- `backend/app/data/seed_attractions.json` - 景点数据

#### Day 12: 攻略社区后端
生成内容：
- `backend/app/models/guide.py` - 攻略模型
- `backend/app/models/interaction.py` - 互动模型（点赞/评论/收藏）
- `backend/app/api/guides.py` - 攻略API
- `backend/app/services/guide_service.py` - 攻略服务
- `backend/app/services/recommend_service.py` - 推荐服务

#### Day 13: 前端搭建
生成内容：
- `frontend/src/main.js` - 入口文件
- `frontend/src/App.vue` - 根组件
- `frontend/src/router/index.js` - 路由配置
- `frontend/src/stores/auth.js` - 认证状态
- `frontend/src/stores/guide.js` - 攻略状态
- `frontend/src/api/index.js` - API封装
- `frontend/src/views/Home.vue` - 首页
- `frontend/src/views/ItineraryGenerator.vue` - AI生成页
- `frontend/src/views/GuideList.vue` - 攻略列表
- `frontend/src/components/common/Navbar.vue` - 导航栏
- `frontend/tailwind.config.js` - Tailwind配置
- `frontend/package.json` - 依赖配置

#### Day 14: 前端剩余页面
生成内容：
- `frontend/src/views/Login.vue` - 登录页
- `frontend/src/views/Register.vue` - 注册页
- `frontend/src/views/GuideDetail.vue` - 攻略详情
- `frontend/src/views/GuideEditor.vue` - 发布攻略
- `frontend/src/views/Profile.vue` - 用户中心
- `frontend/src/components/guide/GuideCard.vue` - 攻略卡片
- `frontend/src/components/itinerary/DayPlan.vue` - 行程展示

#### Day 15: 测试
生成内容：
- `backend/tests/test_auth.py`
- `backend/tests/test_guides.py`
- `backend/tests/test_itinerary.py`
- `backend/tests/conftest.py`

#### Day 16: 部署
生成内容：
- `Dockerfile` (backend)
- `Dockerfile` (frontend)
- `docker-compose.yml`
- `.env.example`
- 部署文档

### Phase 3: 迭代与总结阶段（Day 17-21）

**总结阶段的AI行为准则**：
- ✅ 引导用户反思整个过程
- ✅ 帮助用户提炼学到的PM方法论
- ✅ 协助整理Portfolio展示材料
- ✅ 提供面试演示建议

#### Day 17-19: 文档产出
- `docs/iteration_plan.md` - V2迭代规划
- `docs/retrospective.md` - 产品复盘

#### Day 20-21: Portfolio整理
- 完善README
- 录制演示视频脚本
- 准备面试话术

---

## 代码规范

### 后端代码规范

```python
# 1. 使用类型注解
def generate_itinerary(destination: str, days: int) -> dict:
    pass

# 2. 清晰的函数命名
def should_use_llm(request: dict) -> bool:
    """判断是否需要调用LLM"""
    pass

# 3. 适当的注释
# 热门城市使用规则引擎，节省API成本
if destination in POPULAR_CITIES:
    return rule_engine.generate(destination, days)

# 4. 错误处理
try:
    result = llm_service.generate(prompt)
except Exception as e:
    logger.error(f"LLM generation failed: {e}")
    return fallback_response()
```

### 前端代码规范

```vue
<!-- 1. 组件结构清晰 -->
<template>
  <!-- 模板 -->
</template>

<script setup>
// 逻辑
</script>

<style scoped>
/* 样式 */
</style>

<!-- 2. 使用组合式API -->
<script setup>
import { ref, computed, onMounted } from 'vue'

const guides = ref([])
const loading = ref(false)

const fetchGuides = async () => {
  loading.value = true
  // ...
}
</script>

<!-- 3. 合理的组件拆分 -->
<!-- 单个组件不超过200行 -->
```

---

## 文档规范

### 产品文档模板结构

每份产品文档应包含：
1. **文档信息** - 版本、作者、日期
2. **目录** - 便于快速定位
3. **核心内容** - 结构化、逻辑清晰
4. **附录** - 参考资料、数据来源

### Markdown格式要求

- 使用标准Markdown语法
- 表格对齐整齐
- 代码块指定语言
- 图片使用相对路径

---

## 沟通方式

### 与用户沟通

1. **提问方式**
   - 开放式问题引导思考："你觉得这个功能的核心价值是什么？"
   - 封闭式问题确认细节："MVP阶段是否包含图片上传功能？"

2. **反馈方式**
   - 先肯定优点，再指出改进点
   - 提供具体的改进建议，不只是指出问题
   - 解释"为什么"，不只是"怎么做"

3. **进度同步**
   - 每个阶段开始前，说明目标和产出
   - 每个阶段结束后，总结完成情况
   - 主动提醒下一步工作

---

## 质量标准

### 产品文档质量标准

- ✅ 逻辑自洽，没有前后矛盾
- ✅ 数据有来源，不是拍脑袋
- ✅ 结论有推导过程
- ✅ 专业术语使用准确
- ✅ 格式规范，易于阅读
- ✅ 可以直接用于面试展示

### 代码质量标准

- ✅ 核心功能可运行
- ✅ 代码结构清晰
- ✅ 关键逻辑有注释
- ✅ 错误处理完善
- ✅ 可以本地启动和部署

---

## 特殊说明

### AI能力边界

在技术方案文档中，需要明确说明：
- AI能做什么：生成标准行程、理解复杂需求、个性化推荐
- AI不能做什么：实时数据查询、精确价格计算、预订功能
- 降级方案：LLM失败时使用规则引擎兜底

### 成本控制

- 规则引擎优先，减少LLM调用
- LLM调用使用缓存机制
- 开发阶段使用Mock数据测试

### 时间管理

- 产品设计阶段不要赶进度，质量优先
- 开发阶段可以适当简化，能跑通即可
- 如果时间紧张，优先保证产品文档质量

---

## 禁止行为

❌ **不要**直接生成完整产品文档让用户复制粘贴  
❌ **不要**在产品设计阶段催促用户快速完成  
❌ **不要**使用过于复杂的技术架构  
❌ **不要**引入不必要的第三方服务  
❌ **不要**在用户没有明确需求时自作主张  

---

## 成功标准

项目成功的标志：
1. ✅ 产出9份高质量产品文档
2. ✅ 有一个可运行的线上Demo
3. ✅ 用户理解了PM方法论
4. ✅ 用户可以自信地在面试中展示这个项目
5. ✅ 用户获得了产品思维的训练

---

## 版本信息

- **文档版本**：v1.0
- **创建日期**：2026-05-18
- **适用范围**：TourismAgent项目全周期