# 网站修改总结

## ✅ 已完成的修改

### 1. 论文列表 (data/papers.yml)
- ✅ 删除了原有的所有论文
- ✅ 保留了 Yingying Deng 作为第一作者的 11 篇论文：
  - 2026: Sissi (arXiv)
  - 2025: Z-Magic (CVPR), FireFlow (ICML), Inversion-Free Style Transfer (arXiv)
  - 2024: Z* (CVPR)
  - 2022: StyTr2 (CVPR)
  - 2021: Arbitrary Video Style Transfer (AAAI)
  - 2020: Exploring the representativity (IEEE TMM), Arbitrary style transfer (ACM MM)
  - 2019: Selective clustering (MTAP)
  - 2017: Style-oriented (SIGGRAPH Asia Posters)

### 2. 个人信息 (data/site.yml)
- ✅ title: 改为 "邓盈盈（Yingying Deng）"
- ✅ url: 改为 https://yingyingdeng.github.io
- ✅ author.name: "Yingying Deng"
- ✅ author.name_zh: "邓盈盈"
- ✅ me: [Yingying Deng]
- ✅ scholar_id: 8N8lbJQAAAAJ
- ✅ GitHub 链接更新为 https://github.com/HolmesShuan

### 3. 个人简介 (data/pages/intro.md)
- ✅ 创建了新的个人简介（需要你进一步完善）

### 4. 新闻列表 (data/news.yml)
- ✅ 创建了基于你论文的新闻列表

### 5. README.md
- ✅ 更新了维护说明，改为适合你的内容

### 6. 新增文档
- ✅ DEPLOYMENT.md - 详细的部署指南
- ✅ CHANGES.md - 本修改总结文档

---

## ⚠️ 需要你手动完成的修改

### 必须修改（部署前）

1. **修改邮箱和单位信息** - `data/site.yml`
   ```yaml
   author:
     email: your.email@example.com  # 改为你的真实邮箱
     position: Ph.D. Student        # 改为你的实际职位
     affiliation: University of Science and Technology Beijing  # 改为你的实际单位
   ```

2. **替换头像** - `static/images/avatar.jpg`
   - 将你的照片保存为这个文件（会自动裁剪成正方形）

3. **完善个人简介** - `data/pages/intro.md`
   - 目前是模板内容，需要改成你自己的介绍

### 可选修改（建议完成）

4. **准备代表性工作的图片**
   - 如果想在首页展示代表性工作，需要准备图片放到：
     - `static/images/representative-works/style-transfer.jpg`
     - `static/images/representative-works/diffusion.jpg`
     - `static/images/representative-works/transformers.jpg`
   - 或者删除 `site.yml` 中 `home.representative` 部分

5. **更新新闻** - `data/news.yml`
   - 根据实际情况添加或修改新闻

6. **CV 页面** - `data/cv.yml`（如果需要）
   - 目前还是原来的内容，如需使用需要更新

7. **团队页面** - `data/members.yml`
   - 如果不需要团队页面，可以清空或删除导航中的 Team 链接

---

## 📦 备份文件

以下文件已备份，如需恢复可以使用：
- `data/papers.yml.backup` - 原始论文列表（Fan Tang 的所有论文）
- `data/site.yml.backup` - 原始个人信息

---

## 🚀 下一步：部署

请查看 **DEPLOYMENT.md** 文件，按照步骤部署到 GitHub Pages。

简要步骤：
1. 修改必须的信息（邮箱、单位、头像、简介）
2. 在 GitHub 创建仓库 `你的用户名.github.io`
3. 推送代码到 GitHub
4. 启用 GitHub Pages（Actions）
5. 访问 `https://你的用户名.github.io`

---

## 📊 统计

- 原论文数量：约 100+ 篇
- 现论文数量：11 篇（Yingying Deng 第一作者）
- 修改文件数：6 个
- 新增文件数：2 个
- 备份文件数：2 个

