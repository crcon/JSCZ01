# GitHub Pages 部署修复步骤

## ⚠️ 当前问题
GitHub Pages 返回 404 NOT_FOUND，原因是 Pages 部署源配置不正确。

## ✅ 修复步骤 (这一次要手动做)

### 第1步: 进入仓库设置
1. 打开 https://github.com/crcon/JSCZ01
2. 点击 **Settings** (设置)

### 第2步: 配置 GitHub Pages
1. 在左侧菜单找到 **Pages** (页面)
2. 在 **Build and deployment** 部分:

   **Source** 选择:
   - [ ] GitHub Actions (旧方式)
   - [✓] **Deploy from a branch** (从分支部署) ← 选这个

   **Branch** 选择:
   - [✓] **select branch: main** ← 选 main
   - 选择根目录 **/root**

3. 点击 **Save** 保存

### 第3步: 等待部署
- 第一次部署需要 1-2 分钟
- 部署完成后会收到通知

### 第4步: 访问网站
部署完成后，访问:
```
https://crcon.github.io/JSCZ01/
```

---

## 📊 新的部署配置

已修改工作流文件 (`.github/workflows/deploy.yml`):
- ✅ 使用 `peaceiris/actions-gh-pages` 动作
- ✅ 自动部署到 `gh-pages` 分支
- ✅ 支持自动更新和缓存清理
- ✅ 添加 `.nojekyll` 禁用 Jekyll

---

## 🔄 完整修复流程

```
1. 此配置已推送到 GitHub
2. 静待 GitHub Actions 运行 (1分钟)
3. 手动进入 Settings → Pages
4. 选择 "Deploy from a branch"
5. 选择 "gh-pages" 分支 (或 main 分支)
6. 保存
7. 等待 1-2 分钟
8. 网站上线！
```

---

## 🖼️ 视觉指南

**Settings → Pages 应该看起来像这样:**
```
Build and deployment
├─ Source
│  └─ [Deploy from a branch] ← 选这个
├─ Branch  
│  ├─ [gh-pages branch] ← 自动生成
│  └─ /root (or /(root)) ← 默认根目录
└─ [Save] 保存
```

---

## 💡 链接预览

配置完成后,将能访问:

| 资源 | URL |
|-----|-----|
| 主页 | https://crcon.github.io/JSCZ01/ |
| 中文版 | https://crcon.github.io/JSCZ01/zh-CN/... |
| 下载页 | https://crcon.github.io/JSCZ01/_downloads.html |

---

## ❓ 常见问题

**Q: 为什么还是404?**
A: GitHub Pages 的配置还没保存。确保进入了 Settings → Pages，选择了分支，并点击了 Save

**Q: 等多久?**
A: 首次部署 1-2 分钟。之后每次 push 会自动重新部署

**Q: 能用 GitHub Actions 自动部署吗?**
A: 可以,但需要在 Pages 中选择 "GitHub Actions" 作为 Source(还在测试阶段)

---

## 🚀 确认部署成功的方式

访问: https://github.com/crcon/JSCZ01/actions

如果看到绿色的 ✅ 对勾,表示部署成功。

---

## 📝 已做的修改

- ✅ 更新 `.github/workflows/deploy.yml` (更可靠的部署方式)
- ✅ 添加 `.nojekyll` (禁用 Jekyll)
- ✅ 配置自动推送到 gh-pages
- ✅ 已推送到 GitHub

**现在只需要在 Settings 中手动配置一次即可!**
