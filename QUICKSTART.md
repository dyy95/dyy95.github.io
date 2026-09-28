# 🚀 快速开始

## 第一步：修改个人信息（5分钟）

### 1. 打开 `data/site.yml`，修改以下三处：

```yaml
author:
  email: your.email@example.com       # 👈 改为你的邮箱
  position: Ph.D. Student             # 👈 改为你的职位
  affiliation: University of Science and Technology Beijing  # 👈 改为你的单位
```

### 2. 替换头像

将你的照片复制到：`static/images/avatar.jpg`

### 3. 编辑个人简介

打开 `data/pages/intro.md`，改成你自己的介绍

---

## 第二步：部署到 GitHub（10分钟）

### 1. 在 GitHub 创建仓库

- 仓库名：`你的用户名.github.io`（例如：`yingyingdeng.github.io`）
- 必须选择 **Public**

### 2. 在终端执行以下命令

```bash
cd /Users/yingying/Documents/code/yingyingdeng.github.io

git init
git add .
git commit -m "Initial commit"
git branch -M master
git remote add origin https://github.com/你的用户名/你的用户名.github.io.git
git push -u origin master
```

### 3. 启用 GitHub Pages

1. 进入仓库 **Settings → Pages**
2. **Source** 选择 **GitHub Actions**
3. 回到 **Actions** 标签，点击 **Enable workflows**
4. 点击 **Build & Deploy → Run workflow**

### 4. 等待1-2分钟，访问网站

访问 `https://你的用户名.github.io`

---

## 完成！🎉

日后更新论文或新闻：
1. 修改 `data/papers.yml` 或 `data/news.yml`
2. 执行：`git add . && git commit -m "Update" && git push`
3. 等待1分钟，网站自动更新

---

## 📚 详细文档

- **DEPLOYMENT.md** - 完整部署指南（包含常见问题）
- **CHANGES.md** - 所有修改的详细说明
- **README.md** - 日常维护说明

## ⚠️ 如果遇到问题

查看 **DEPLOYMENT.md** 的"常见问题"部分，或在仓库 Actions 页面查看错误日志。
