# prd — PRD 生成器

把一句话需求变成结构化 PRD 的技能（snarktank/ralph 上游汉化版）：先问 3-5 个选择题澄清，再产出带用户故事/验收标准/功能需求/非目标的完整需求文档。

## 相关技能

- [agent-config-sync-check](https://github.com/huzhw/agent-config-sync-check)：八端同步守卫：链接/硬链接/README 同步检查与修复
- [git-commit](https://github.com/huzhw/git-commit-skill)：Git 提交规范
- [daily-record-gitlab-md](https://github.com/huzhw/daily-record-gitlab-md-skill)：日报记录（第一步）
- [daily-merge-gitlab-excel](https://github.com/huzhw/daily-merge-gitlab-excel-skill)：日报合并（手动兜底，已由日报管家接管，不推荐）
- [code-check](https://github.com/huzhw/code-check-skill)：增量代码隐患检查
- [deepseek-harness-settings-curator](https://github.com/huzhw/deepseek-harness-settings-curator)：DeepSeek Harness 模型配置梳理
- [deepseek-harness-plugin-doctor](https://github.com/huzhw/deepseek-harness-plugin-doctor)：DeepSeek Harness 插件与升级体检医生
- [reread-rules](https://github.com/huzhw/reread-rules-skill)：重载 CLAUDE.md / AGENTS.md 规则
- [dev-env-upgrade](https://github.com/huzhw/dev-env-upgrade)：开发环境升级医生：版本体检/最新版查询/安全升级
- [ralph](https://github.com/huzhw/ralph-skill)：PRD 转 prd.json（Ralph 自主执行格式）
- [coding-rules](https://github.com/huzhw/coding-rules)：编码规则库（独立仓库，非 skill）
- [daily-report-panel](https://github.com/huzhw/daily-report-panel)：日报管家（关联仓库，非 skill，自动合并/导出/发件）
- [memory-ai-cleanup](https://github.com/huzhw/memory-ai-cleanup)：memory-ai 记录定期清理：删过期流水、摘索引死链、清 tmp 残留
- [ssh-transfer](https://github.com/huzhw/ssh-transfer)：服务器传文件走命令行（scp/sftp 流式，字节不进模型上下文）

## 解决了什么问题

需求一句话丢过来就开写代码，边界不清、验收标准靠感觉，做完才发现理解偏了。这个技能强制两步走：先用带字母选项的选择题把歧义问掉（用户回 "1A, 2C, 3B" 即可），再按固定模板产出 PRD——用户故事小而具体、验收标准可验证、非目标划清边界。产出直接可喂给 [ralph](https://github.com/huzhw/ralph-skill) 转 prd.json 进自主执行循环。

## 使用

对 AI 说触发词即可：

- "写 prd"、"生成 prd"、"需求文档"、"出 prd"
- "create a prd"、"write prd for"、"plan this feature"、"spec out"

AI 会先问 3-5 个澄清选择题，按答案生成 `tasks/prd-<feature-name>.md`。

## 文件结构

```
prd/
├── SKILL.md           # 技能本体（frontmatter name/description + 完整模板与示例）
├── README.md          # 本文件
├── JUNCTION说明.md    # 五端 Junction 指向关系（agent-config-sync-check 自动维护）
└── .gitignore
```

## 安装

```bash
git clone https://github.com/huzhw/prd-skill.git ~/.claude/skills/prd
```

重启 Claude Code 生效。

## 许可

MIT（上游 snarktank/ralph 同 license）
