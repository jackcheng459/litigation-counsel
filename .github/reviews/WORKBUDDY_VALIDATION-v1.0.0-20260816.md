# WorkBuddy 隔离校验回执

- 候选版本：`litigation-counsel v1.0.0`
- 日期：2026-08-16
- 校验对象：更新后的完整候选目录树
- 隔离配置目录：`/private/tmp/litigation-counsel-final-validation.zfNmYs`
- 真实 WorkBuddy 市场：未修改

## 校验步骤与结果

1. 将候选仓库复制到隔离配置的 `plugins/marketplaces/my-experts/plugins/litigation-counsel`，排除 `.git`。
2. 设置隔离的 `WORKBUDDY_CONFIG_DIR`，调用当前 WorkBuddy 应用内置 `validate_expert.py`。
3. 校验器返回：`Expert package is valid!`，无错误、无警告。
4. 在同一隔离市场调用内置 `register_expert.py`。
5. 注册器返回：`Registered 'litigation-counsel' in marketplace.json`。
6. 对生成的 `marketplace.json` 执行 JSON 解析，解析通过，source 为 `./plugins/litigation-counsel`。

## 其他机械检查

- `.codebuddy-plugin/plugin.json` 可解析。
- `displayDescription.zh` 为 48 字，符合当前校验器建议的 40 至 50 字。
- Agent、两个 Skill 和六个 references 路径均存在；Markdown 相对链接检查通过。
- 两个 Skill frontmatter 均有且仅有一组起止分隔符；主文件分别为 92 行和 134 行。
- 头像为 512 × 512、8-bit RGB PNG。
- 排除 `.git` 后未发现软链接或可执行文件。
- `git diff --check` 通过。

## 未覆盖项

- 未在真实 WorkBuddy 界面替换或重载当前已安装专家。
- 未使用真实案件材料进行行为测试。
- 未创建 Git 标签、GitHub Release，也未更改仓库可见性。
