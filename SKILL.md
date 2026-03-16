---
name: github-skill-publish
description: 一键完成 OpenClaw Skill 发布到 GitHub，自动初始化、提交、推送代码，支持添加赞赏码
version: 1.0.0
author: HansXu-1986
license: MIT
---

# 🚀 github-skill-publish - OpenClaw Skill 一键发布到 GitHub

自动化完成 OpenClaw Skill 开发后的发布全流程，从本地初始化 git 到推送 GitHub，一步到位。

## ✨ 特性

- 🚀 **一键自动化** - 自动完成 git 初始化、提交、远程设置、推送全过程
- 📝 **模板生成** - 自动生成标准 SKILL.md 框架
- 💰 **收款集成** - 支持添加支付宝/微信赞赏码，一键插入到技能说明
- ✅ **符合规范** - 生成的技能完全符合 OpenClaw SkillHub 规范

## When to use

Use this skill when:

1. You have developed a new OpenClaw skill locally
2. You want to publish it to GitHub for sharing on SkillHub
3. You need to add donation QR code for supporting development
4. You want the whole process automated instead of manual steps

## Instructions

### 🚀 Publishing Flow

1. **Pre-requirements**:
   - User has created an empty repository on GitHub
   - User has a Personal Access Token (PAT) with repo permissions
   - Skill has been created locally in `skills/skill-name` with SKILL.md

2. **Collect information**:
   - GitHub username
   - GitHub repository name (usually same as skill name)
   - Personal Access Token (PAT)
   - (Optional) Donation QR code image URL

3. **Automated process**:
   - Initialize git in skill directory
   - Configure git user if needed
   - Add all files
   - Commit with standard message
   - Set remote origin with PAT authentication
   - Rename branch to `main`
   - Push to GitHub
   - If donation QR provided, update SKILL.md to add donation section

4. **Output result**:
   - Show success message
   - Give install command for users: `npx skills add username/repo -s skill-name -g -y`
   - Share the GitHub URL

### ⚠️ Error Handling

- Repository not found → Ask user to check if repository is created on GitHub
- Authentication failed → Ask user to verify PAT and permissions
- Branch name conflict → Force push confirmation
- Skill directory not found → Ask user to create skill first with `npx skills init`

## Configuration

No configuration needed, all parameters collected interactively when publishing.

## Pricing

- 🎉 **完全免费** - 开源工具，帮助更多人发布 Skill
- 如果对你有帮助，欢迎赞赏支持开发 👇

![支付宝赞赏码](https://pcsdata.baidu.com/thumbnail/0105b65d3hc459885de5ae19b517cfa7?fid=843748537-16051585-645516420529129&rt=pr&sign=FDTAER-yUdy3dSFZ0SVxtzShv1zcMqd-2sh4WyLvEGJkEXw3S2lFgGSAX8M%3D&expires=2h&chkv=0&chkbd=0&chkpc=&dp-logid=575398625919898124&dp-callid=0&time=1773633600&bus_no=26&size=c1600_u1600&quality=100&vuk=-&ft=video)

## Changelog

### 1.0.0 (2026-03-16)
- Initial release
- Automate the whole publishing process
- Support adding donation QR code
- Fully compliant with OpenClaw SkillHub standards
