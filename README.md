# Job Apply Skill

一个面向中国校园招聘场景的 Codex Skill，用于查找正式校招岗位、核验投递规则、辅助填写网申、记录投递状态，并在用户自行配置后同步个人飞书多维表格。

## 能做什么

- 使用 ego lite 打开企业官方校招网站并筛选岗位
- 核验岗位届别、开放状态、城市、截止时间和投递规则
- 在用户确认具体岗位与具体简历后辅助完成网申
- 提交前逐项复核个人信息，并保留最终确认步骤
- 使用本地台账记录投递结果
- 可选同步到使用者自己的飞书多维表格

## 安装

将仓库克隆或下载到 Codex Skills 目录：

```text
~/.codex/skills/job-apply
```

重新打开 Codex 对话后，可以直接说：

```text
调用 job apply，帮我查找某公司的正式校招岗位
```

## 首次配置

1. 复制 `references/personal-info-template.json`，在 `records/` 下创建自己的个人信息文件，并创建一个空的 `records/applications.jsonl` 作为本地投递台账。
2. 在 `config.json` 中配置岗位偏好；手机号可以留空，在实际登录时临时提供。
3. 如需飞书同步，请先创建自己的多维表格，再将链接写入 `config.json` 的 `tracking.table_url`，并把 `tracking.enabled` 改为 `true`。
4. 如果没有飞书表格，Skill 会提示创建，也可以只使用本地 `records/applications.jsonl`。

推荐的飞书字段：公司名称、事业部&岗位、岗位类型、投递时间、进度、岗位链接。

## 隐私与安全

- 本仓库不包含作者的姓名、手机号、邮箱、学校、简历、历史投递记录或飞书链接。
- 不要把个人资料、简历、验证码或自己的飞书链接提交到公开仓库。
- Skill 不会使用作者、分享者、教程截图或示例中的飞书表格。
- 未经用户确认具体岗位和具体简历，不会开始网申；默认在最终提交前再次确认。

## 目录

```text
job-apply/
├── SKILL.md
├── config.json
├── agents/openai.yaml
├── records/                  # 本地创建，不提交个人数据
└── references/
    ├── companies.md
    ├── form-filling-guide.md
    └── personal-info-template.json
```

## 说明

招聘网站及投递规则会持续变化。使用时应以企业官方招聘页面的当前信息为准，公开社区中的求职进度只能作为未经企业验证的参考。

## License

[MIT License](LICENSE)
