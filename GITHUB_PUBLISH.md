# GitHub发布指南

## 项目已准备就绪！

本地Git仓库已初始化并完成了首次提交。现在需要上传到GitHub。

### 📋 准备步骤

#### 步骤1: 在GitHub上创建新仓库

1. 访问 [github.com/new](https://github.com/new)
2. 填写仓库信息：
   - **Repository name**: `JSCZ01`
   - **Description**: `Jiangsu Independent Energy Storage Revenue Calculator - 江苏独立储能收益测算模型`
   - **Visibility**: 选择 `Public` (公开) 或 `Private` (私有)
   - **Initialize this repository with**: 不勾选任何选项 (因为我们已有本地仓库)

3. 点击 "Create repository"

#### 步骤2: 建立远程连接

创建后，GitHub会显示命令行指引。需要在本地执行：

```bash
cd "/Users/c/Desktop/2.0 储能电站/JS  江苏常州/1.1 融资方案/江苏省独立储能电能量收益测算（白色背景版本）.ai"

# 添加远程仓库
git remote add origin https://github.com/YOUR_USERNAME/JSCZ01.git

# 重命名分支为main (推荐)
git branch -M main

# 推送到GitHub
git push -u origin main
```

**替换 `YOUR_USERNAME` 为你的GitHub用户名**

#### 步骤3: 设置SSH密钥 (可选但推荐)

如果之前没有设置SSH密钥，可以生成一个：

```bash
# 生成SSH密钥
ssh-keygen -t ed25519 -C "your_email@example.com"

# 复制公钥
cat ~/.ssh/id_ed25519.pub

# 在GitHub设置中添加
# Settings > SSH and GPG keys > New SSH key
```

然后使用SSH方式：

```bash
git remote set-url origin git@github.com:YOUR_USERNAME/JSCZ01.git
```

### 🚀 完整命令流程

如果你已经有GitHub账户，执行以下命令：

```bash
# 1. 进入项目目录
cd "/Users/c/Desktop/2.0 储能电站/JS  江苏常州/1.1 融资方案/江苏省独立储能电能量收益测算（白色背景版本）.ai"

# 2. 添加远程仓库
git remote add origin https://github.com/YOUR_USERNAME/JSCZ01.git

# 3. 重命名分支
git branch -M main

# 4. 推送所有内容
git push -u origin main

# 5. 验证
git remote -v
```

### 📊 项目统计

- **文件总数**: 170+
- **代码行数**: 3000+
- **主要语言**: HTML, JavaScript, CSS
- **文档**: README.md, DESIGN.md, CONTRIBUTING.md, LICENSE
- **多语言支持**: 40+种语言

### ✨ 发布后的下一步

#### 1. 启用GitHub Pages (可选)

如果你想通过GitHub Pages发布网站：

1. 进入仓库的 **Settings**
2. 找到 **Pages** 选项
3. 选择 **Source** 为 `main` 分支
4. 配置 **/root** 作为发布源

网站将在 `https://YOUR_USERNAME.github.io/JSCZ01/` 上发布

#### 2. 添加Topics

在仓库主页的右侧，点击 **Add topics**，添加相关标签：
- `energy-storage`
- `calculator`
- `renewable-energy`
- `investment-analysis`
- `jiangsu`
- `finance`
- `multilingual`
- `next-js`

#### 3. 添加社交预览

1. 在仓库 **Settings** 中找到 **Social preview**
2. 上传一张 **1280×640px** 的预览图

#### 4. 设置README徽章

在README顶部添加：

```markdown
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub stars](https://img.shields.io/github/stars/YOUR_USERNAME/JSCZ01.svg?style=social&label=Star)](https://github.com/YOUR_USERNAME/JSCZ01)
[![GitHub forks](https://img.shields.io/github/forks/YOUR_USERNAME/JSCZ01.svg?style=social&label=Fork)](https://github.com/YOUR_USERNAME/JSCZ01)
```

#### 5. 配置CI/CD (可选)

创建 `.github/workflows/deploy.yml` 实现自动部署：

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: '18'
      - run: npm install
      - run: npm run build
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./out
```

### 🔗 项目链接格式

发布后，项目可通过以下方式访问：

```
GitHub仓库: https://github.com/YOUR_USERNAME/JSCZ01
GitHub Pages: https://YOUR_USERNAME.github.io/JSCZ01/
主页面: https://YOUR_USERNAME.github.io/JSCZ01/_downloads.html
中文版: https://YOUR_USERNAME.github.io/JSCZ01/zh-CN/agents/web-creator/share/6953a0a4f028f342ba34e29e.html
```

### 💡 推荐的GitHub配置

#### 分支保护规则

1. 进入 **Settings** > **Branches**
2. 添加分支保护规则 (`main`):
   - ✅ Require pull request reviews
   - ✅ Dismiss stale pull request approvals
   - ✅ Require status checks to pass

#### Issues模板

创建 `.github/ISSUE_TEMPLATE/bug_report.md`:

```markdown
---
name: Bug Report
about: 报告bug
---

## 描述问题
[问题描述]

## 重现步骤
1. 打开...
2. 点击...
3. 发生...

## 预期行为
[预期行为]

## 环境信息
- 浏览器: [如: Chrome 120]
- 操作系统: [如: macOS 14]
- 语言版本: [如: zh-CN]
```

### 📝 维护建议

1. **定期更新README** - 随着项目演进更新文档
2. **标记Release** - 发布重要版本时创建Release标签
3. **监控Issues** - 及时响应用户反馈
4. **社区互动** - 参与相关讨论和Discussions

### 🆘 常见问题

**Q: 我是第一次使用GitHub**
A: GitHub提供了详细的新手指南，访问 https://docs.github.com/cn

**Q: 如何更新仓库内容?**
A: 
```bash
git add .
git commit -m "描述你的改动"
git push origin main
```

**Q: 如何处理冲突?**
A: 建议从官方文档学习：https://docs.github.com/cn/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts

### 📞 获取帮助

- GitHub文档: https://docs.github.com
- GitHub社区: https://github.community
- Stack Overflow: https://stackoverflow.com/questions/tagged/github

---

**提示**: 上传成功后，可以在GitHub仓库中看到所有文件、提交历史和文档。

**下一步**: 按照上面的步骤在GitHub上创建 `JSCZ01` 仓库，然后执行推送命令！
