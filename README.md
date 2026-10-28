# 智快问卷定义规范

一套可交换的问卷 JSON 定义格式，用于问卷的导入与导出。不限于智快问卷使用——任何系统都可以用这套格式来描述一份收集表单。

## 快速开始

复制下面这段 JSON，喂给任何 AI 助手：

> "请按这个 JSON 格式生成一份活动报名问卷，包含姓名、手机号、备注三个字段"

```json
{
  "schemaVersion": "1.0",
  "title": "活动报名表",
  "questions": [
    { "id": "name", "type": "text", "title": "姓名", "required": true },
    { "id": "phone", "type": "phone", "title": "手机号", "required": true },
    { "id": "remark", "type": "textarea", "title": "备注" }
  ]
}