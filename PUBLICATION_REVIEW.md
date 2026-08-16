# litigation-counsel v1.0.0 发布候选核验记录

核验日期：2026-08-16

发布分支：`agent/publish-v1.0.0-preview`

状态：`READY_FOR_HUMAN_MERGE_REVIEW`

## 发布范围

本仓库仅承载 `litigation-counsel` 专家及发布审计记录：

- `.codebuddy-plugin/plugin.json`
- `agents/litigation-counsel.md`
- `skills/litigation-case-workflow`
- `skills/legal-collab-toolkit`
- `avatars/expert.png`
- `README.md`
- `CHANGELOG.md`
- `.github/reviews/`

本仓库不包含客户材料、案件原件、密钥、备份目录或真实案件运行记录。

## 已闭合的预览问题

- README 的 5 处占位内容已全部替换。
- `legal-collab-toolkit` 声明的两个 references 已随包提供。
- Agent 不再引用未打包的外部 Skill；两个运行 Skill 均在 plugin 清单中声明。
- 数据边界已升级为绿色、黄色、红色、红线四类链路准入规则。
- 已补齐 CHANGELOG、正式版本说明、机械校验与独立复核记录。
- 作者信息已由通用占位更新为程建都。
- `displayDescription.zh` 已缩短为 48 字，处于校验器建议的 40 至 50 字区间。
- 固定期限表述已移除，改用正式程序文书、送达证据、现行官方法源和双人复算。

## 校验结论

- WorkBuddy 当前内置 `validate_expert.py` 对完整目录树校验通过，无错误、无警告。
- 当前内置 `register_expert.py` 已在 `/private/tmp` 独立配置目录注册成功，未修改真实 WorkBuddy 市场。
- plugin 清单为有效 JSON；Agent、Skill 和 references 路径均可解析。
- 两个 Skill 的 frontmatter 完整，Skill 主文件均少于 500 行。
- 头像为 512 × 512 PNG。
- 未发现包内软链接、可执行文件、密钥、Token、密码、真实案号或客户材料。
- Claude CLI 独立复核使用 `claude-opus-5`、`max effort`、只读工具集，结论为 `PASS_WITH_NOTES`；其 P1 已闭合，P2 已逐项处理或确认不纳入发布包。

详细证据见 `.github/reviews/`。

## 发布闸门

- Private 仓库与 Draft PR：已允许。
- 合并至 `main`：等待 Jack 单独审阅与明确授权。
- 改为 Public：等待 Jack 单独明确授权。
- 创建 `v1.0.0` 标签和 GitHub Release：暂不执行。
- 删除发布分支：暂不执行，保留回退与审计路径。
