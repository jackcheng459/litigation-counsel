# litigation-counsel v1.0.0 预览核验记录

核验日期：2026-08-15

发布分支：`agent/publish-v1.0.0-preview`

## 发布范围

本仓库仅承载 `litigation-counsel` 专家本体：

- `.codebuddy-plugin/plugin.json`
- `agents/litigation-counsel.md`
- `skills/legal-collab-toolkit`
- `avatars/expert.png`
- `README.md`

本仓库不包含客户材料、案件原件、密钥、备份目录或内部审计运行记录。

## 机械校验

- WorkBuddy `expert-manager` v0.1.0 基础结构校验通过。
- 警告为 `displayDescription.zh` 长度 112 字，超过建议的 40 至 50 字。
- plugin 清单为有效 JSON。
- 头像为 512 x 512 PNG。
- 未发现软链接、可执行文件、API Key、Token、密码、真实案号或客户材料。
- 公开联系方式为 `wx1811985798`。

## 待闭合问题

- README 仍有 5 处 `[TODO]` 占位。
- `skills/legal-collab-toolkit/SKILL.md` 声明的两个 references 尚未随包提供。
- Agent frontmatter 引用了外部 `ai-legal-case-workflow`，但该 Skill 未随包提供，也未在 plugin 清单中声明依赖。
- 数据安全章节仍采用“红级仅本地处理”的旧口径，需要升级为绿色、黄色、红色、红线四类链路准入规则。
- 缺少独立 CHANGELOG、完整复核回执和正式版本更新说明。
- `author.name` 仍为通用占位 `WorkBuddy User`，公开前应确认是否改为真实作者名。

## 发布闸门

- Private 仓库与 Draft PR：已允许。
- 当前仅为预览候选，不得宣称正式放行。
- 合并至 `main`：等待上述问题整改和 Jack 审阅。
- 改为 Public：等待 Jack 单独明确授权。
- 创建 `v1.0.0` 标签和 GitHub Release：暂不执行。
