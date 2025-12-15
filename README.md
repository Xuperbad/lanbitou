# 申论学习笔记

这是一个基于 Docusaurus 构建的申论文章站点，用于收集、整理和学习申论相关的官媒文章。

## 🚀 快速开始

### 本地开发

1. 克隆或进入项目目录：
```bash
cd lanbitou
```

2. 安装依赖：
```bash
npm install
```

3. 启动开发服务器：
```bash
npm start
```

浏览器会自动打开 `http://localhost:3000`

### 构建生产版本

```bash
npm run build
```

构建后的静态文件会生成在 `build` 目录。

## 📝 如何添加文章

### 方法一：在 docs 目录添加文档

1. 在 `docs` 目录下选择或创建合适的分类文件夹
2. 创建 Markdown 文件（`.md` 或 `.mdx`）
3. 添加 frontmatter 和内容：

```markdown
---
sidebar_position: 1
---

# 文章标题

> 来源：人民日报
> 日期：2024年12月

## 原文内容

文章正文...

## 文章分析

分析内容...
```

### 方法二：在 blog 目录添加学习笔记

1. 在 `blog` 目录创建文件，文件名格式：`YYYY-MM-DD-标题.md`
2. 添加内容：

```markdown
---
slug: 文章slug
title: 文章标题
authors: [你的名字]
tags: [标签1, 标签2]
---

学习笔记内容...
```

## 🗂️ 目录结构

```
lanbitou/
├── .github/
│   └── workflows/
│       └── deploy.yml # GitHub Actions 部署配置
├── docs/              # 文档目录（文章库）
│   ├── intro.md      # 首页介绍
│   ├── 时政热点/      # 时政类文章
│   └── 写作技巧/      # 写作方法
├── blog/             # 博客目录（学习笔记）
├── src/              # 源代码
│   └── pages/        # 自定义页面
├── static/           # 静态资源
├── docusaurus.config.js  # 配置文件
└── package.json      # 依赖配置
```

## 🌐 部署到 GitHub Pages

### 第一步：配置 GitHub 仓库

1. 在 GitHub 创建一个名为 `lanbitou` 的仓库
2. 修改 `docusaurus.config.js` 中的配置：
   - 将所有 `YOUR_GITHUB_USERNAME` 替换为你的 GitHub 用户名

### 第二步：推送代码到 GitHub

在项目根目录（`d:\AppDev\lanbitou`）执行：

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/lanbitou.git
git push -u origin main
```

### 第三步：启用 GitHub Pages

1. 进入 GitHub 仓库的 Settings
2. 点击左侧的 "Pages"
3. 在 "Build and deployment" 部分：
   - Source 选择 "GitHub Actions"
4. 等待 Actions 自动运行完成

### 第四步：访问你的站点

部署成功后，访问：`https://YOUR_GITHUB_USERNAME.github.io/lanbitou/`

## 💡 使用建议

1. **定期更新**：养成定期收集和整理文章的习惯
2. **分类清晰**：按主题分类，便于查找和复习
3. **深度分析**：不只是复制文章，要加入自己的分析和理解
4. **标签管理**：使用标签系统，方便按主题检索

## 🔧 常用命令

```bash
npm start              # 启动开发服务器
npm run build          # 构建生产版本
npm run serve          # 本地预览构建结果
npm run clear          # 清除缓存
```

## 📚 学习资源

- [Docusaurus 官方文档](https://docusaurus.io/)
- [Markdown 语法指南](https://www.markdownguide.org/)

---

Built with [Docusaurus](https://docusaurus.io/)
