# study-planner — 学习路径设计师

确定学习目标 → 搜索最新学习资源 → 设计逐天教学计划 → 产出 learning-coach 兼容的计划文件。

不执行教学，只设计路径。

## 什么时候用

- 知道要学什么但不知道怎么拆成每天进度
- 需要一份结构化的学习计划（概念依赖 ≤ 2/天）
- 需要 learning-coach 可消费的教学规则和计划文件
- 不确定怎么验证学习成果（需要设计验证点）

## 前置条件

如果连学什么都不知道，它会建议先用 [career-advisor](https://github.com/liu-jie-liang/career-advisor) 确定职业方向。有 CAREER-PROFILE.md 时可跳过已覆盖维度。

## 安装

```bash
cp -r study-planner ~/.trae/skills/
```

## 使用

```
Use Skill: study-planner
```

它分四步走：问（结构化提问）→ 查（搜索最新资源）→ 拆（设计逐天计划，每天 ≤ 2 个新概念）→ 存（产出 CONTEXT.md + PROFILE.md）。产出给 learning-coach 消费。

## 调用链

```
career-advisor → study-planner → learning-coach
    确定学什么      设计怎么学      逐天执行教学
```

## 已验证

与 career-advisor + learning-coach 贯穿测试通过：career-advisor 确定 Java+AI 方向 → study-planner 设计 12 周计划 → learning-coach 逐天执行。
