# 邓盈盈个人主页 · 维护说明

网站地址：<https://yingyingdeng.github.io>

日常更新只需要改 `data/` 目录下的几个文本文件，保存并推送到 GitHub 后，大约 1 分钟网站自动更新。
Google Scholar 引用数和 GitHub star 数每天自动抓取，不用手动维护。

```
data/                  ← 日常只改这里
├── papers.yml         论文（新增论文就改这个）
├── venues.yml         会议/期刊表：简称、全称、CCF 等级（遇到新会议时加一条）
├── news.yml           新闻
├── cv.yml             CV 页面
├── site.yml           个人信息、导航、首页代表性工作（很少改）
├── pages/intro.md     首页个人简介
└── metrics.json       引用数 / star 数（自动生成，不要手改）
static/                图片、PDF 等，原样发布到网站根目录
  ├── images/          照片、论文缩略图等
  └── files/           想放到网站上的 PDF 等
templates/  build.py  scripts/   网站程序（一般不用动）
```

---

## 一、新增论文

打开 `data/papers.yml`，把下面这段粘贴到列表最上面，改成实际内容：

```yaml
- title: "Paper Title: With a Colon Needs Quotes"
  authors: [Yingying Deng, Author Two, Author Three]
  venue: CVPR
  year: 2027
  links:
    arxiv: https://arxiv.org/abs/2701.xxxxx
    code: https://github.com/username/repo
```

详细说明请参考原 README 文档。

---

## 二、新增新闻

打开 `data/news.yml`，在最上面加：

```yaml
- date: 2026-09-28
  icon: "🎉"
  text: "Our paper **XXX** was accepted to **CVPR 2027**!"
```

---

## 三、修改个人信息

修改 `data/site.yml` 中的以下字段：
- `author.position`: 你的职位
- `author.affiliation`: 你的单位
- `author.email`: 你的邮箱
- `author.links.github`: 你的 GitHub 地址

修改 `data/pages/intro.md` 来更新首页的个人简介。

---

## 四、部署网站

### 方式 A：GitHub Pages（推荐）

1. **创建 GitHub 仓库**
   - 仓库名必须是：`你的GitHub用户名.github.io`（例如：`yingyingdeng.github.io`）
   - 设为 Public

2. **推送代码到 GitHub**
   ```bash
   cd /Users/yingying/Documents/code/yingyingdeng.github.io
   git init
   git add .
   git commit -m "Initial commit: Personal homepage"
   git branch -M master
   git remote add origin https://github.com/你的用户名/yingyingdeng.github.io.git
   git push -u origin master
   ```

3. **启用 GitHub Actions**
   - 进入仓库 **Settings → Pages**
   - **Build and deployment → Source** 选择 **GitHub Actions**
   - 回到仓库首页，进入 **Actions** 标签
   - 如提示启用 workflow，点击启用
   - 点击 **Build & Deploy** → **Run workflow** 手动运行一次

4. **等待构建完成**
   - 大约 1-2 分钟后，访问 `https://你的用户名.github.io` 即可看到网站

### 方式 B：本地预览

```bash
pip install -r requirements.txt     # 第一次需要
python build.py --serve             # 预览：http://localhost:8000
```

---

## 五、重要提醒

1. **替换头像**：将你的照片放到 `static/images/avatar.jpg`
2. **修改邮箱**：在 `data/site.yml` 中修改 `author.email`
3. **修改职位和单位**：在 `data/site.yml` 中修改 `author.position` 和 `author.affiliation`
4. **修改个人简介**：编辑 `data/pages/intro.md`
5. **添加代表性工作的图片**：可以暂时删除或替换 `static/images/representative-works/` 下的图片

---

## 六、自动更新引用数

每天凌晨会自动抓取 Google Scholar 的引用数和 GitHub star 数。如果需要手动触发：
- 进入仓库 **Actions → Build & Deploy → Run workflow**

---

如有问题，请参考原项目文档或查看 `.github/workflows/deploy.yml` 配置文件。
