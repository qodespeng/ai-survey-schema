# 变更记录

## 1.1.0 (2026-11-25)

### Schema
- 规范版本号升级至 `1.1`
- 新增顶层 `settings` 运行配置集合：支持开放时间窗口（`startAt` / `endAt`）、未开始/截止自定义提示与行为（`beforeStartMessage` / `afterEndAction` / `afterEndMessage`）、访问口令与匿名控制（`accessPassword` / `passwordHint` / `disallowAnonymous`）、提交限额与重入策略（`maxRecordsPerUser` / `totalSubmitLimit` / `reenterAction`）及自定义提交成功提示（`submitSuccessMessage`）
- 新增下拉选择问题类型 `select`（目前共支持 15 种问题类型）
- 问题字段新增 `shortTitle`（移动端/表头短标题）、`unique`（全表唯一性校验）、`readOnly`（只读展示控制）及 `roles`（`list` / `query` / `identity` 数据列表与检索角色标记）
- 为选择题 `options` 增加 `uniqueItems: true` 选项去重校验
- 完善 `literalRuleSpec` 规则说明：明确指定存放 AI 评估结果的目标字段默认具备只读属性（`readOnly=true`）

## 1.0.0 (2026-10-28)

首个公开版本。

### Schema
- 定义问卷标题、描述、问题列表的顶层结构
- 支持 14 种问题类型：text / textarea / integer / decimal / radio / checkbox / email / phone / date / datetime / yesno / row / column / matrix / grid
- 支持容器嵌套（row / column / grid / matrix）
- 支持 AI 评估规则配置（literalRuleSpec / ruleExecutable / ruleResultRequired）
- 支持渐进式填写和随机排序

### 脚本参考
- 支持 ASSERT / DISABLES / HIDEROWS / HIDES / JUMPS / RANGE / REPEAT 命令
- 支持算术、字符串、日期时间、其他四类函数
- 支持算术、逻辑、关系三类操作符
