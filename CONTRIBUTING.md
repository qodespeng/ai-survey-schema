# 贡献指南

## 修改 Schema

1. 修改 `schema/survey.schema.json`。
2. 同步更新 `examples/` 下的示例文件，确保仍能通过校验。
3. 在 `CHANGELOG.md` 中记录变更。

## 修改脚本参考

1. 修改 `docs/script-reference.md`。
2. 如果新增命令或函数，同时在 `examples/with-script.json` 中添加示例。

## 提交信息

使用简短的英文描述，例如：
- `fix: correct JUMPS example in script reference`
- `feat: add rating field type to schema`

## 版本发布

- 每次发布在 `CHANGELOG.md` 顶部新增一个版本条目。
- 主版本变更需在 README 的版本策略部分说明迁移方式。