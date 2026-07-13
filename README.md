# study-planner — 学习路径设计师

**确定学习目标 → 搜索最新学习资源 → 设计逐天教学计划 → 产出 learning-coach 兼容的 CONTEXT.md + PROFILE.md。**

不执行教学，只设计路径。产出给 `learning-coach` 使用。

## 调用链中的位置

```
career-advisor          study-planner          learning-coach
    │                       │                       │
    ├─ 诊断职业方向          ├─ 读取 CAREER-PROFILE.md  ├─ 读取 CONTEXT.md
    ├─ 市场数据验证          ├─ 搜最新学习路径           ├─ 读取 PROFILE.md
    ├─ 输出 CAREER-PROFILE ─→├─ 输出 CONTEXT.md ───────→├─ 生成教学文件
    │                       ├─ 输出 PROFILE.md ────────→├─ 追踪进度 + 错题
    │                       │                       │
    ▼                       ▼                       ▼
  确定学什么              设计怎么学              逐天执行教学
```

- **上游依赖**：`career-advisor`（可选，优先读取 CAREER-PROFILE.md 避免重复提问）
- **下游消费者**：`learning-coach`（必需，读取 CONTEXT.md + PROFILE.md 执行教学）
- **搜索规则**：继承 `web-verify` 的信源过滤策略

## 它解决什么问题

你知道要学什么但不知道怎么拆成每天的进度。study-planner 做四件事：

1. **结构化提问**：搞清楚目标、基础、时间、约束（如果 CAREER-PROFILE.md 已有则跳过已覆盖维度）
2. **按需搜索**：就业市场数据、考试大纲、技术版本，用 `web-verify` 级信源过滤
3. **逐天拆解**：每天 ≤ 2 个新概念，教学三件套（teaching + exercises + solutions），阶段整合日
4. **产出两份文件**：CONTEXT.md（规则）+ PROFILE.md（学习者画像 + 计划 + 全景图）

## 安装

```bash
mkdir -p ~/.trae/skills/study-planner
cp SKILL.md ~/.trae/skills/study-planner/
```

## 使用

```
Use Skill: study-planner
```

如果不知道学什么，它会建议先用 `career-advisor` 确定职业方向。

## 已验证

与 career-advisor + learning-coach 贯穿测试通过：career-advisor 确定 Java+AI 方向 → study-planner 设计 12 周计划 → learning-coach 逐天执行。
