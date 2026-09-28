# 网站部署指南

## 📋 部署前准备

在部署之前，请先完成以下修改：

### 1. 必须修改的信息

打开 `data/site.yml`，修改以下内容：

```yaml
author:
  email: your.email@example.com       # 改为你的真实邮箱
  position: Ph.D. Student             # 改为你的实际职位
  affiliation: University of Science and Technology Beijing  # 改为你的实际单位
```

### 2. 替换头像

将你的照片放到 `static/images/avatar.jpg`（会自动裁剪成正方形）

### 3. 修改个人简介

编辑 `data/pages/intro.md`，写入你自己的介绍

---

## 🚀 部署到 GitHub Pages

### 第一步：创建 GitHub 仓库

1. 登录 GitHub，点击右上角 **+** → **New repository**
2. **Repository name** 必须填写：`你的GitHub用户名.github.io`
   - 例如：如果你的 GitHub 用户名是 `yingyingdeng`，仓库名就是 `yingyingdeng.github.io`
3. 选择 **Public**（必须是公开仓库）
4. **不要勾选** "Add a README file"
5. 点击 **Create repository**

### 第二步：推送代码到 GitHub

在终端中执行以下命令：

```bash
cd /Users/yingying/Documents/code/yingyingdeng.github.io

# 初始化 git 仓库
git init

# 添加所有文件
git add .

# 提交
git commit -m "Initial commit: Personal homepage"

# 设置主分支名为 master
git branch -M master

# 添加远程仓库（请替换为你的实际用户名）
git remote add origin https://github.com/你的用户名/yingyingdeng.github.io.git

# 推送到 GitHub
git push -u origin master
```

**注意**：如果推送时提示需要登录，可能需要：
- 使用 Personal Access Token（在 GitHub Settings → Developer settings → Personal access tokens 中生成）
- 或者配置 SSH 密钥

### 第三步：启用 GitHub Pages

1. 在 GitHub 仓库页面，点击 **Settings**
2. 在左侧菜单找到 **Pages**
3. 在 **Build and deployment** 下：
   - **Source** 选择 **GitHub Actions**
4. 回到仓库首页，点击 **Actions** 标签
5. 如果看到提示，点击 **Enable workflows**
6. 点击左侧的 **Build & Deploy** workflow
7. 点击右侧的 **Run workflow** → **Run workflow** 手动触发一次

### 第四步：等待构建完成

1. 在 Actions 页面可以看到构建进度
2. 等待显示绿色的 ✓（大约 1-2 分钟）
3. 访问 `https://你的用户名.github.io` 查看网站

---

## 🔄 日常更新

修改完文件后，推送更新：

```bash
git add .
git commit -m "Update papers/news/profile"
git push
```

每次推送后，网站会自动重新构建（约 1 分钟）。

---

## 📝 本地预览

在推送前可以先本地预览：

```bash
# 安装依赖（首次需要）
pip install -r requirements.txt

# 启动预览
python build.py --serve
```

然后访问 http://localhost:8000

---

## ✅ 常见问题

### 1. 推送失败，提示权限不足

**方法 A：使用 Personal Access Token**
```bash
# 在 GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
# 点击 Generate new token，勾选 repo 权限
# 复制生成的 token，在推送时用 token 作为密码
```

**方法 B：使用 SSH**
```bash
# 生成 SSH 密钥
ssh-keygen -t ed25519 -C "your.email@example.com"

# 将公钥添加到 GitHub Settings → SSH and GPG keys
cat ~/.ssh/id_ed25519.pub

# 修改 remote URL
git remote set-url origin git@github.com:你的用户名/yingyingdeng.github.io.git
```

### 2. 网站构建失败（Actions 显示红色 ✗）

点击失败的 workflow 查看日志，通常是因为：
- `papers.yml` 或其他 YAML 文件格式错误
- 缩进不对齐
- 标题中有冒号但没加引号

### 3. 如何更换 GitHub Pages 地址

如果仓库名不是 `用户名.github.io`，网站地址会是 `https://用户名.github.io/仓库名/`。
需要修改 `data/site.yml` 中的 `url` 字段。

---

## 🎯 下一步

部署完成后，建议：

1. ✅ 修改 `data/site.yml` 中的真实邮箱和单位信息
2. ✅ 替换 `static/images/avatar.jpg` 为你的照片
3. ✅ 编辑 `data/pages/intro.md` 写入个人简介
4. ✅ 根据需要添加新闻到 `data/news.yml`
5. ✅ 准备代表性工作的图片放到 `static/images/representative-works/`
6. ✅ 如需简历页面，编辑 `data/cv.yml`

---

祝部署顺利！🎉
