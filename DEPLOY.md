# 🚀 部署到 GitHub Pages 完整指南

## 📋 前置条件

- 一个 GitHub 账号（免费）
- 浏览器

## ✅ 分步部署指南

### 第1步：在 GitHub 创建仓库

1. 登录 [GitHub.com](https://github.com)
2. 点击右上角 `+` → `New repository`
3. 填写信息：
   - **Repository name**: `mlb-stats-app`（或其他名称）
   - **Description**: `MLB 打者统计查询应用`
   - **Public** ✓（选择公开）
   - 其他选项保持默认

4. 点击 `Create repository`

### 第2步：上传文件

#### 方式 A：使用 GitHub 网页界面（推荐初学者）

1. 进入你新创建的仓库
2. 点击 `Add file` → `Upload files`
3. 拖拽或选择以下文件：
   - `index.html`
   - `README.md`
   - `DEPLOY.md`

4. 在 "Commit changes" 中填写：
   - Commit message: `Add MLB stats app`
5. 点击 `Commit changes`

#### 方式 B：使用 Git 命令行

```bash
# 1. 在本地创建文件夹
mkdir mlb-stats-app
cd mlb-stats-app

# 2. 初始化 Git 仓库
git init

# 3. 添加你的文件到此文件夹
# 将 index.html、README.md 等文件复制到此文件夹

# 4. 配置 Git（首次使用需要）
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"

# 5. 添加文件到 Git
git add .

# 6. 提交
git commit -m "Initial commit: Add MLB stats app"

# 7. 连接到远程仓库
git remote add origin https://github.com/你的用户名/mlb-stats-app.git

# 8. 推送到 GitHub
git branch -M main
git push -u origin main
```

### 第3步：启用 GitHub Pages

1. 进入仓库页面
2. 点击 `Settings`（设置）标签
3. 在左侧菜单找到 `Pages`
4. 在 "Build and deployment" 部分：
   - **Source**: 选择 `Deploy from a branch`
   - **Branch**: 选择 `main`，文件夹选择 `/ (root)`
5. 点击 `Save`

### 第4步：等待部署

- 稍等 1-2 分钟，GitHub 会自动构建和部署
- 刷新 Settings > Pages 页面，会看到：
  ```
  ✅ Your site is published at https://你的用户名.github.io/mlb-stats-app/
  ```

### 第5步：访问你的网站

在浏览器中打开：
```
https://你的用户名.github.io/mlb-stats-app/
```

🎉 完成！

---

## 🔄 更新网站

如果你想更新内容（修改代码、添加功能等）：

### 使用网页界面：
1. 进入仓库
2. 找到要编辑的文件（如 `index.html`）
3. 点击 ✏️ 编辑
4. 修改内容
5. Commit changes

### 使用命令行：
```bash
# 修改本地文件后
git add .
git commit -m "Update: 修改说明"
git push origin main
```

---

## 📝 常见问题

### Q1：网站显示 404？
**A:**
- 检查仓库是否是公开的
- 确认 GitHub Pages 已启用
- 等待 2-3 分钟再刷新
- 清除浏览器缓存（Ctrl+Shift+Del）

### Q2：部署后网站是空白的？
**A:**
- 确认 `index.html` 是否上传到仓库根目录
- 检查浏览器控制台（F12）是否有错误
- 尝试清除缓存并重新加载

### Q3：如何使用自己的域名？
**A:**
1. 购买域名（如在 Godaddy、Namecheap 等）
2. 进入 Settings > Pages
3. 在 "Custom domain" 输入你的域名
4. 按照提示配置 DNS 记录

### Q4：可以使用子域名吗？
**A:** 可以。如果仓库名是 `mlb-stats-app`，URL 会自动是：
```
https://你的用户名.github.io/mlb-stats-app/
```

### Q5：每次更新后网站需要多长时间刷新？
**A:** 通常 1-2 分钟，刷新浏览器即可看到更新。

---

## 🎯 额外优化建议

### 1. 添加 .gitignore（可选）
创建文件 `.gitignore`：
```
# 系统文件
.DS_Store
Thumbs.db

# 编辑器文件
.vscode/
.idea/

# 日志
*.log
```

### 2. 使用更好的项目描述

在 GitHub 仓库主页点击 `About`（关于）→ 编辑：
- **Description**: `MLB 打者统计查询应用 - 使用官方 MLB Stats API`
- **Website**: 输入你的 GitHub Pages URL
- **Topics**: `mlb`, `baseball`, `sports`, `statistics`

### 3. 添加 LICENSE（许可证）

1. 进入仓库
2. 点击 `Add file` → `Create new file`
3. 文件名: `LICENSE`
4. 选择许可证模板（如 MIT）
5. Commit

---

## 📚 进阶使用

### 使用 GitHub Desktop（图形界面）

如果你不习惯命令行，可以使用 GitHub Desktop：

1. 下载 [GitHub Desktop](https://desktop.github.com/)
2. 登录你的 GitHub 账号
3. 点击 "Clone repository"
4. 选择你的 `mlb-stats-app` 仓库
5. 编辑文件
6. 点击 "Commit to main"
7. 点击 "Push origin"

### 关于仓库大小限制

- GitHub 每个仓库建议不超过 1GB
- 单个文件建议不超过 100MB
- 本项目只有 HTML/CSS/JS，远小于限制

---

## ✨ 功能验证清单

部署完成后，逐项检查：

- [ ] 网站可以访问
- [ ] 搜索框能够输入
- [ ] 能够搜索到打者
- [ ] 点击打者能显示统计数据
- [ ] 表格数据正确显示
- [ ] 在手机上也能正常显示（响应式）
- [ ] 所有链接都能工作

---

## 📞 需要帮助？

### 常用 Git 命令

```bash
# 查看状态
git status

# 查看提交历史
git log

# 回退到上一个版本
git revert HEAD

# 更新本地代码（同步远程）
git pull origin main
```

### 官方资源

- [GitHub Pages 官方文档](https://docs.github.com/en/pages)
- [Git 官方指南](https://git-scm.com/book)
- [GitHub 学习资源](https://skills.github.com/)

---

## 🎉 大功告成！

你现在拥有一个在线的 MLB 打者统计应用！

**分享你的网站：**
```
https://你的用户名.github.io/mlb-stats-app/
```

祝使用愉快！⚾

---

**最后更新**: 2024年8月
