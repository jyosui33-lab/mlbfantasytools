# ⚾ MLB 打者统计查询应用

一个专业的 MLB（美国职业棒球大联盟）打者统计查询网页应用，支持实时数据查询和分析。

## 🎯 功能特性

- **🔍 打者搜索** - 快速搜索 MLB 打者
- **📊 本季统计** - 查看本赛季的详细统计数据（打数、安打、本垒打、打率等）
- **📈 近7场成绩** - 查看打者最近7场比赛的单场数据
- **⚡ 今日对阵** - 查看今天的比赛对手和先发投手
- **💾 实时更新** - 使用 MLB Stats API 获取最新数据

## 🛠️ 技术栈

- **前端框架**: 纯 HTML/CSS/JavaScript（无需构建工具）
- **数据来源**: [MLB Stats API](https://statsapi.mlb.com/api)
- **样式设计**: 专业体育统计风格（深色主题 + 棒球场绿 + 金色强调）
- **响应式**: 支持桌面端和移动端

## 📱 设计亮点

| 元素 | 颜色 | 说明 |
|------|------|------|
| 背景 | `#1a1a1a` | 深灰黑（夜间棒球场氛围） |
| 主色 | `#0C5C0C` | 棒球场绿 |
| 强调 | `#FFB81C` | MLB 金色 |
| 文本 | `#ffffff` | 白色高对比度 |

## 🚀 快速开始

### 本地运行

1. **克隆或下载项目**
   ```bash
   git clone https://github.com/你的用户名/mlb-stats-app.git
   cd mlb-stats-app
   ```

2. **直接打开** `index.html`
   - 在浏览器中打开 `index.html` 文件即可使用
   - 无需安装任何依赖或运行构建命令

### 部署到 GitHub Pages

#### 方法 1：使用 GitHub Web 界面

1. **在 GitHub 上创建新仓库**
   - 仓库名: `mlb-stats-app` 或任意名称
   - 设为公开仓库

2. **上传文件**
   - 将 `index.html` 上传到仓库根目录
   - （可选）上传 `README.md`

3. **启用 GitHub Pages**
   - 进入仓库的 Settings
   - 找到 "Pages" 选项
   - 在 "Source" 中选择 "main" 分支
   - 点击 Save

4. **访问你的网站**
   - 稍等几分钟，访问 `https://你的用户名.github.io/mlb-stats-app`

#### 方法 2：使用 Git 命令行

```bash
# 初始化本地仓库
git init

# 添加文件
git add index.html README.md

# 提交
git commit -m "Initial commit: MLB stats app"

# 连接到远程仓库
git remote add origin https://github.com/你的用户名/mlb-stats-app.git

# 推送到 GitHub
git branch -M main
git push -u origin main
```

然后在 GitHub 仓库设置中启用 Pages（同上）。

## 📖 使用说明

### 1. 搜索打者
- 在顶部搜索框输入打者名字
- 系统会实时显示匹配的打者列表
- 点击想要查看的打者

### 2. 查看统计数据
选中打者后，页面会显示：
- **本季统计**: 打数、安打、本垒打、打点、打率、上垒率、长打率、OPS
- **近7场成绩**: 每场比赛的单场数据
- **今日对阵**: 如果今天有比赛，会显示对手球队和先发投手

### 3. 数据说明

| 缩写 | 含义 | 说明 |
|------|------|------|
| AB | At Bats | 打数 |
| H | Hits | 安打 |
| HR | Home Runs | 本垒打 |
| RBI | Runs Batted In | 打点 |
| AVG | Batting Average | 打率 |
| OBP | On-Base Percentage | 上垒率 |
| SLG | Slugging Percentage | 长打率 |
| OPS | On-Base Plus Slugging | 上垒加长打率 |

## 🌐 API 来源

本应用使用免费的 [MLB Stats API](https://statsapi.mlb.com/):
- 无需 API Key
- 实时数据
- 包含完整的球员、比赛、统计数据

## ⚙️ 技术细节

### 文件结构
```
mlb-stats-app/
├── index.html          # 主应用文件（包含 HTML、CSS、JavaScript）
├── README.md          # 本说明文档
└── mlb-stats-app.jsx  # React 版本（可选，用于本地开发）
```

### 核心功能实现

#### 搜索打者
```javascript
const response = await fetch(
  `https://statsapi.mlb.com/api/v1/people/search?query=${query}`
);
```

#### 获取打者统计
```javascript
const response = await fetch(
  `https://statsapi.mlb.com/api/v1/people/${playerId}/stat?group=hitting&type=season`
);
```

#### 获取比赛日志
```javascript
const response = await fetch(
  `https://statsapi.mlb.com/api/v1/people/${playerId}/stat?group=hitting&type=gameLog&limit=7`
);
```

#### 获取今日比赛
```javascript
const response = await fetch(
  `https://statsapi.mlb.com/api/v1/schedule?sportId=1&date=${today}`
);
```

## 📝 浏览器兼容性

- ✅ Chrome / Edge (最新版)
- ✅ Firefox (最新版)
- ✅ Safari (最新版)
- ✅ 移动浏览器

## 🎨 自定义

### 修改配色方案

在 `index.html` 的 `<style>` 中修改以下变量：

```css
/* 修改这些颜色值 */
background-color: #1a1a1a;    /* 背景色 */
border: 2px solid #0C5C0C;    /* 边框色 */
color: #FFB81C;               /* 强调色 */
```

### 修改字体

在 `<head>` 中修改：
```html
<style>
  body {
    font-family: '你的字体名', monospace;
  }
</style>
```

## 🐛 常见问题

**Q: 为什么搜索无结果？**
- A: 检查名字拼写，MLB API 对拼写敏感。可以尝试只输入名字的一部分。

**Q: 数据为什么不是最新的？**
- A: MLB Stats API 数据可能有 5-15 分钟的延迟，这是正常的。

**Q: 可以离线使用吗？**
- A: 不可以，需要网络连接以获取 MLB 数据。

**Q: 如何部署到自己的域名？**
- A: 购买域名后，在 GitHub Pages 设置中添加自定义域名。

## 📊 功能路线图

- [ ] 添加多打者对比功能
- [ ] 投手数据查询
- [ ] 球队统计
- [ ] 数据导出（CSV/Excel）
- [ ] 历史数据查询
- [ ] 收藏夹功能
- [ ] 暗/亮主题切换

## 📄 许可证

MIT License - 自由使用和修改

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📧 联系方式

如有问题或建议，欢迎通过以下方式联系：
- GitHub Issues
- 提交 Pull Request

---

**最后更新**: 2024年8月
**版本**: 1.0.0

祝你使用愉快！⚾
