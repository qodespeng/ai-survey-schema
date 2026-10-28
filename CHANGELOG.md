# 变更记录

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