# 江苏独立储能收益测算模型

一个专业的在线计算工具平台，用于计算独立运营的储能项目的收益。

🌐 **多语言支持** | 🔧 **实时计算** | 📊 **详细分析** | 🎯 **融资决策**

## 项目简介

本项目是一个针对江苏省独立储能电能量项目的**收益计算和融资分析工具**，主要服务于：
- 财务分析师
- 项目开发商
- 能源投资机构
- 清洁能源行业专业人士

## 核心功能

### 📋 项目参数输入
用户可以输入以下关键参数：
- **装机容量** (MW) - 储能系统的额定功率
- **储能时长** (MWh) - 能量存储容量
- **充放电效率** (%) - 系统往返效率
- **电力市场价格** (¥/MWh) - 平均电价
- **运营周期** (次/年) - 年投入产出次数
- **政策补贴** (¥/MWh) - 政策性价格补贴

### 🧮 智能计算引擎
系统支持以下场景计算：
- ☀️ **夏季调峰期** - 峰谷价差收益
- 🌙 **非夏季期** - 基础调度收益
- 💰 **税收激励** - 政策优惠考虑
- 🎯 **成本分摊** - 运维成本计算

### 📊 收益分析输出
- 年度总收益预测
- 场景对比分析
- 敏感性分析
- 投资回报期 (IRR, NPV)
- 融资可行性评估

## 技术栈

### 前端框架
- **Next.js** - React框架，支持静态生成和服务端渲染
- **TypeScript** - 类型安全的JavaScript
- **Ant Design** - 企业级UI组件库
- **CSS-in-JS** - 动态样式管理 

### 国际化 (i18n)
支持40+种语言：
- 中文简体、繁体 (zh-CN, zh-TW)
- 英文 (en)
- 主要欧洲语言 (es, fr, de, it, pt, ru, pl, etc.)
- 亚洲语言 (ja, ko, hi, vi, th, etc.)
- 中东、非洲语言 (ar, he, ur, sw, etc.)

### 部署
- 静态资源：Next.js静态export
- 资源管理：CDN分布式存储
- 性能监控：Microsoft Clarity集成

## 项目结构

```
.
├── README.md                          # 项目说明文档
├── DESIGN.md                          # 系统设计文档
├── _downloads.html                    # 下载入口页面
├── favicon.ico                        # 网站图标
├── icon※1ee2af4e3832d5d5.png         # 品牌图标
├── wisebase-static/                   # Next.js静态资源
│   ├── _next/                         # 编译输出
│   │   ├── static/
│   │   │   ├── css/                   # 样式表
│   │   │   ├── chunks/                # JS代码段
│   │   │   └── media/                 # 多媒体资源
│   │   ├── broadcast-channel.js       # 跨选项卡通信
│   │   └── init-clarity.js            # 分析追踪
│
└── [locale]/                          # 多语言版本目录 (40+语言)
    └── agents/
        └── web-creator/
            └── share/
                └── 6953a0a4f028f342ba34e29e.html  # 计算工具页面
```

### 多语言支持列表
- 欧洲语言: en, es, fr, de, it, pt, ru, pl, ca, da, nl, no, sv, cs, sk, sl, hr, hu, et, lt, lv, ro
- 亚洲语言: zh-CN, zh-TW, ja, ko, hi, vi, th, bn, ta, te, mr, gu, kn, ml
- 中东/非洲: ar, fa, he, ur, sw
- 其他: am, fil, bg

## 使用方式

### 本地查看
```bash
# 这是一个静态网站,可直接用浏览器打开
open _downloads.html

# 或启动本地服务器
python -m http.server 8000
# 访问: http://localhost:8000
```

### 在线访问
访问生成的网址查看各语言版本：
- 中文简体: `[域名]/zh-CN/agents/web-creator/share/6953a0a4f028f342ba34e29e.html`
- 中文繁体: `[域名]/zh-TW/agents/web-creator/share/6953a0a4f028f342ba34e29e.html`
- 英文: `[域名]/en/agents/web-creator/share/6953a0a4f028f342ba34e29e.html`

## 核心计算逻辑

### 主要公式
```
年收益 = (峰时收益 + 谷时收益 + 政策补贴) × 运营周期 - 运维成本

其中:
  峰时收益 = 装机容量 × 峰谷价差 × 储能时长 × 充放电效率
  政策补贴 = 储能容量 × 补贴价格
  运维成本 = 装机容量 × 年运维费率
```

### 场景分析
- **夏季调峰**: 利用峰谷价差,重点关注高温期用电峰值
- **其他季节**: 参与市场调度,获得调度费收入
- **政策激励**: 考虑清洁能源补贴、可调度资源补偿等

## 主要特性

✅ **实时计算** - 毫秒级响应,支持参数实时调整
✅ **多场景模型** - 支持不同运营策略的收益计算
✅ **详细报告** - 生成专业的财务分析报告
✅ **全球化** - 40+种语言本地化
✅ **响应式设计** - 完美支持桌面、平板、手机
✅ **易于集成** - 可嵌入其他平台
✅ **隐私友好** - 所有计算在客户端进行

## 数据安全

- ✅ 所有计算在浏览器本地完成,无需上传到服务器
- ✅ 不收集用户输入的商业敏感信息
- ✅ 支持完全离线使用

## 开发指南

### 必要环境
- Node.js 18.x 或更高版本
- npm 或 pnpm

### 本地开发
```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build

# 导出静态资源
npm run export
```

## 部署方案

### 方案1: 静态主机 (推荐)
- GitHub Pages
- Vercel
- Netlify
- CDN服务

### 方案2: 容器化部署
```bash
# 构建Docker镜像
docker build -t energy-calculator .

# 运行容器
docker run -p 3000:3000 energy-calculator
```

## 文件清单

| 文件/目录 | 说明 | 大小 |
|---------|------|------|
| _downloads.html | 主入口页面 | <5KB |
| wisebase-static/_next/static/css/ | 样式表 | ~200KB |
| wisebase-static/_next/static/chunks/ | JavaScript代码 | ~1.5MB |
| wisebase-static/broadcast-channel.js | 跨标签页通信 | ~10KB |
| wisebase-static/init-clarity.js | 用户行为追踪 | ~5KB |
| [locale]/agents/web-creator/share/ | 多语言页面 | ~4KB × 40 |

**总体积**: ~2.5MB (包含所有40语言版本)

## 配置说明

### SEO优化
- ✅ Hreflang标签支持多语言SEO
- ✅ Open Graph metadata用于社交分享
- ✅ Twitter Card支持
- ✅ Canonical链接管理

### 性能
- ✅ CSS-in-JS动态注入 (Ant Design)
- ✅ 代码分割和异步加载
- ✅ 图像优化
- ✅ 资产压缩

### 分析
- 集成Microsoft Clarity进行用户行为分析
- 支持自定义事件追踪

## 下一步计划

- [ ] 接入API获取实时电力市场价格
- [ ] 支持导出PDF报告
- [ ] 添加更多融资模型 (PPP、融资租赁等)
- [ ] 集成地理位置功能,自动填充本地政策参数
- [ ] 移动App版本
- [ ] 支持批量项目投资组合分析

## 贡献指南

欢迎提交Issue和Pull Request!

## 许可证

MIT License - 详见 [LICENSE](LICENSE) 文件

## 联系方式

- 📧 邮箱: [contact@example.com]
- 🐛 问题报告: [GitHub Issues]
- 💬 讨论区: [GitHub Discussions]

---

**最后更新**: 2026年3月17日  
**版本**: 1.0.0  
**作者**: 江苏省储能项目融资分析团队
