# ⚡ GitHub Pages 快速修复 (2分钟)

## 🎯 需要做的事

GitHub Pages 需要在仓库设置中配置一次。按照以下步骤操作:

---

## 步骤 1: 打开设置页面
📍 进入: https://github.com/crcon/JSCZ01/settings/pages

---

## 步骤 2: 配置 Pages Source

**Build and deployment** 部分:

```
Source 选择:
  ☑ Deploy from a branch (从分支部署)

Branch 选择:
  Branch: main ⬅ 重要!
  Directory: /(root) 或 /root
  
[Save] 保存按钮 ← 一定要点击!
```

### 📸 示意图
```
┌─ Build and deployment ─────────┐
│                                 │
│ Source                          │
│ ◉ Deploy from a branch          │
│   Branch: main                  │
│   Directory: /(root)            │
│                                 │
│ [Save] 保存                     │ ← 点这里
└─────────────────────────────────┘
```

---

## 步骤 3: 等待部署 (1-2分钟)

部署会自动开始,可以在 Actions 标签页查看:
https://github.com/crcon/JSCZ01/actions

成功时会显示: ✅ Deploy to GitHub Pages

---

## 步骤 4: 访问网站

部署完成后,访问:

```
https://crcon.github.io/JSCZ01/
```

## ✨ 应该看到中文计算工具页面!

---

## 🔗 分享链接

配置完成后,可以分享给同事:

**直接工具链接:**
```
https://crcon.github.io/JSCZ01/zh-CN/agents/web-creator/share/6953a0a4f028f342ba34e29e.html
```

**主页:**
```
https://crcon.github.io/JSCZ01/
```

---

## ✅ 完成检查清单

- [ ] 打开 https://github.com/crcon/JSCZ01/settings/pages
- [ ] 选择 "Deploy from a branch"
- [x] 已选择 "main" 分支
- [ ] 点击 [Save] 保存
- [ ] 等待 1-2 分钟
- [ ] 访问 https://crcon.github.io/JSCZ01/

---

## 🆘 遇到问题?

**还是404?**
- 清除浏览器缓存 (Ctrl+Shift+Delete)
- 再等 30 秒再刷新
- 检查是否真的点击了 [Save]

**无法访问GitHub?**
- 检查网络连接
- 尝试用隐私模式访问

---

这就是全部! 非常简单。配置一次后会自动部署,之后每次提交代码都会自动更新网站。

**现在立即去配置吧! 🚀**
