# 智快问卷定义规范 (AI Survey Schema)

一套面向 AI 时代的可交换问卷 JSON 定义规范（JSON Schema Draft-07），用于结构化问卷与数据收集表单的生成、校验、导入与导出。

该规范不仅适用于 **AI•智快问卷**，任何需要通过大模型（LLM）自动生成表单、或实现跨平台问卷数据互通的系统均可直接复用。

---

## 在线应用与落地案例

本规范已在 **AI•智快问卷** 中完整落地并投入生产使用：

- **多端覆盖**：已上线 **微信小程序、抖音小程序、支付宝小程序**（搜索 `智快问卷` 或 `AI智快问卷` 即可免费使用），支持三端同步发布与数据收集。
- **核心能力**：
  - **对话式 AI 生成与修改**：用自然语言描述需求（如“生成一份互联网公司员工满意度调查问卷”），自动拆解维度并生成标准量表与逻辑校验脚本。
  - **轻量级数据收集与导出**：个人及日常调研免费使用，支持手机端直接导出 Excel 报表及自然语言数据统计分析。
  - **AI 规则评估与海报分享**：支持配置自然语言评估规则（`literalRuleSpec`），提交后由大模型自动生成个性化评估结果与分享海报。
- **官方网站与更多文档**：[https://qodes.cn](https://qodes.cn)

---

## 规范核心特性 (v1.1)

1. **丰富的题型支持（15 种）**：
   - **基础输入型**：单行文本（`text`）、多行文本（`textarea`）、整数（`integer`）、小数（`decimal`）、邮箱（`email`）、手机号（`phone`）、日期（`date`）、日期时间（`datetime`）。
   - **选择型**：单选（`radio`）、多选（`checkbox`）、下拉选择（`select`）、是/否开关（`yesno`）。
   - **容器与矩阵布局**：单行容器（`row`）、多行容器（`column`）、表格布局（`grid`）、矩阵量表（`matrix`）。
2. **完整的运行与权限控制（`settings`）**：
   - 支持开放时间窗口（`startAt` / `endAt`）、未开始/截止自定义提示与只读回看策略（`afterEndAction`）。
   - 支持访问口令保护（`accessPassword`）、单用户提交次数限制（`maxRecordsPerUser`）、总收集上限（`totalSubmitLimit`）及再次进入行为控制（`reenterAction`）。
3. **企业级数据管理字段属性**：
   - 支持字段全表唯一性校验（`unique`）、只读字段展示（`readOnly`）、移动端短标题适配（`shortTitle`）以及数据列表与检索角色标记（`roles`: `list` / `query` / `identity`）。
4. **逻辑脚本与 AI 评估双引擎**：
   - 支持控件级逻辑控制脚本（`script`，兼容 Epidata CHK 语法，支持跳转、隐藏、范围断言等）。
   - 支持顶层自然语言评估规范（`literalRuleSpec`），可指定将 AI 评估结果自动回填至只读字段。

---

## 目录结构

```text
├── schema/
│   └── survey.schema.json      # JSON Schema 定义文件 (v1.1)
├── docs/
│   └── script-reference.md     # 控件逻辑脚本语法参考手册
├── examples/
│   ├── minimal.json            # 最简活动报名表示例
│   ├── with-rule.json          # 包含 AI 自然语言评估规则与只读结果字段示例
│   ├── with-script.json        # 包含字段级逻辑校验脚本示例
│   └── with-settings.json      # 包含运行配置、下拉选择及唯一性校验的 HR 培训报名示例
├── CHANGELOG.md                # 版本变更记录
└── CONTRIBUTING.md             # 贡献与版本发布指南
