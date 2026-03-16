---
name: github-skill-publish
description: 一键完成 OpenClaw Skill 发布到 GitHub，支持自动创建仓库、自动初始化、提交、推送，支持添加赞赏码
version: 1.1.0
author: HansXu-1986
license: MIT
---

# 🚀 github-skill-publish - OpenClaw Skill 一键发布到 GitHub

自动化完成 OpenClaw Skill 开发后的发布全流程，**支持自动创建 GitHub 仓库**，从本地到线上一步到位，真正一键发布。

## ✨ 特性

- 🚀 **真正一键到底** - 支持**自动创建 GitHub 仓库**，无需手动网站操作
- 🚀 **全自动流程** - 自动完成 git 初始化、配置用户、提交、远程设置、推送全过程
- 📝 **标准模板** - 生成的 SKILL.md 完全符合 OpenClaw 规范
- 💰 **收款集成** - 支持添加支付宝/微信赞赏码，一键插入到技能说明
- ✅ **符合规范** - 生成的技能完美适配火山引擎 SkillHub

## When to use

Use this skill when:

1. You have developed a new OpenClaw skill locally (`npx skills init` done)
2. You want to publish it to GitHub completely automatically
3. You don't want to manually open website to create repository
4. You need to add donation QR code for supporting development
5. You want the whole publishing process automated

## Instructions

### 🚀 Publishing Flow

### Option 1: 全自动（推荐，无需手动创建仓库）

1. **Pre-requirements**:
   - You have created a new skill locally with `npx skills init skill-name`
   - You have a GitHub Personal Access Token (PAT) with `repo` permissions
   - PAT saved or provided when publishing

2. **Collect information**:
   - GitHub username
   - GitHub Personal Access Token (PAT)
   - Skill name (same as local directory name)
   - (Optional) Donation QR code image URL

3. **Automated process**:
   - **Auto-create GitHub repository** via GitHub API 🆕
   - Initialize git in skill directory
   - Configure git user.name and user.email
   - Add all files
   - Commit with standard message
   - Set remote origin with PAT authentication
   - Rename branch to `main`
   - Push to GitHub (created just now!)
   - If donation QR provided, update SKILL.md to add donation section

4. **Output result**:
   - Show success message with GitHub URL
   - Give install command for users: `npx skills add username/repo -s skill-name -g -y`
   - Everything done!

### Option 2: 手动创建仓库（兼容旧流程）

If you already created repository on GitHub manually:

1. **Pre-requirements**:
   - Empty repository created on GitHub
   - Skill already created locally
   - GitHub PAT

2. Same as before - automation will do everything except create repo

### ⚠️ Error Handling

- Authentication failed → Ask user to verify PAT and `repo` permission
- Repository already exists → Ask user to confirm force push
- Skill directory not found → Ask user to create skill first with `npx skills init`
- API creation failed → Show error message, fall back to manual creation

## Configuration

You can save your GitHub username and PAT in `config.json` for future use:

```json
{
  "github_username": "your-github-username",
  "github_token": "ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```

If config exists, you don't need to input username and token every time.

## Pricing

- 🎉 **完全免费** - 开源工具，帮助更多开发者发布 Skill
- 如果对你有帮助，欢迎赞赏支持开发 👇

![支付宝赞赏码](https://pcsdata.baidu.com/thumbnail/0105b65d3hc459885de5ae19b517cfa7?fid=843748537-16051585-645516420529129&rt=pr&sign=FDTAER-yUdy3dSFZ0SVxtzShv1zcMqd-2sh4WyLvEGJkEXw3S2lFgGSAX8M%3D&expires=2h&chkv=0&chkbd=0&chkpc=&dp-logid=575398625919898124&dp-callid=0&time=1773633600&bus_no=26&size=c1600_u1600&quality=100&vuk=-&ft=video)

## 💬 反馈与建议

如果你使用中遇到问题，或者有好的建议，欢迎反馈：

- 🐛 **问题报告**: [点击这里报告 Bug](https://github.com/HansXu-1986/github-skill-publish/issues/new)
- 💡 **功能建议**: [点击这里提建议](https://github.com/HansXu-1986/github-skill-publish/issues/new)

感谢你的反馈，帮助我们做得更好 🙏

## Changelog

### 1.1.0 (2026-03-16)
- ✨ **New**: Add auto-create GitHub repository via API
- ✨ Add configuration support for username and PAT
- 🔧 Keep compatibility with manual create mode
- 📝 Improve documentation

### 1.0.0 (2026-03-16)
- Initial release
- Automate the whole publishing process
- Support adding donation QR code
- Fully compliant with OpenClaw SkillHub standards
