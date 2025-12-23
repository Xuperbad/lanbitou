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

## 📝 文章编写工作流

### 🔄 日常工作流程

#### 1️⃣ **本地开发模式**（推荐用于写作）

```bash
# 启动开发服务器（只需执行一次）
npm start
```

- ✅ **自动热更新**：修改文章后保存，浏览器会自动刷新显示最新内容
- ✅ **实时预览**：边写边看效果，无需手动刷新
- ✅ **无需构建**：不需要每次都 build
- 🌐 访问地址：`http://localhost:3000/lanbitou/`

**工作流程：**
1. 运行 `npm start` 启动开发服务器
2. 在 `blog` 目录创建或编辑文章
3. 保存文件后，浏览器自动刷新显示最新内容
4. 继续编辑，实时查看效果
5. 写完后关闭开发服务器即可（Ctrl+C）

#### 2️⃣ **发布到 GitHub Pages**

```bash
# 方式一：推送到 GitHub，自动部署（推荐）
git add .
git commit -m "添加新文章"
git push

# 方式二：本地构建测试
npm run build    # 构建生产版本
npm run serve    # 本地预览构建结果
```

- ✅ **自动部署**：推送到 GitHub 后，GitHub Actions 会自动构建和部署
- ✅ **无需手动 build**：GitHub Actions 会自动执行构建
- ⏱️ **等待时间**：通常 2-5 分钟后网站更新

### 📄 如何添加文章

在 `blog` 目录创建文件，文件名格式：`YYYY-MM-DD-标题.md`

```markdown
---
slug: 文章slug
title: 文章标题
authors: [你的名字]
tags: [标签1, 标签2]
---

文章内容...
```

### ✨ Markdown 增强功能

#### 🖍️ 马克笔标注（高亮文本）

使用 `==文字==` 语法可以创建马克笔高亮效果：

```markdown
这是 ==默认黄色高亮== 的文字

这是 =r=红色标注== 的重点内容

这是 =b=蓝色标注== 的补充说明

这是 =g=绿色标注== 的正面案例

这是 =o=橙色标注== 的警示内容

这是 =p=紫色标注== 的特殊标记
```

**支持的颜色：**
- 默认：`==文字==` → 黄色高亮
- 红色：`=r=文字==` → 重点、错误
- 蓝色：`=b=文字==` → 补充、说明
- 绿色：`=g=文字==` → 正确、成功
- 橙色：`=o=文字==` → 警告、注意
- 紫色：`=p=文字==` → 特殊、强调
- 粉色：`=q=文字==` → 引用、摘录
- 青色：`=c=文字==` → 信息、提示

**注意事项：**
- ⚠️ 双等号必须紧贴内容，不能有空格：`==文字==` ✅  `== 文字 ==` ❌
- ⚠️ 颜色标记在开头，结尾用双等号：`=r=文字==` ✅  `=r=文字=r=` ❌

## 🗂️ 目录结构

```
lanbitou/
├── .github/
│   └── workflows/
│       └── deploy.yml        # GitHub Actions 自动部署配置
├── blog/                     # 📝 博客文章目录（主要工作区）
│   ├── 2024-12-23-文章.md    # 文章文件（YYYY-MM-DD-标题.md）
│   ├── authors.yml           # 作者信息配置
│   └── tags.yml              # 标签配置
├── src/                      # 源代码
│   ├── css/
│   │   └── custom.css        # 自定义样式（包含马克笔样式）
│   └── pages/                # 自定义页面
├── static/                   # 静态资源（图片等）
├── docusaurus.config.js      # 站点配置文件
├── package.json              # 依赖配置
└── README.md                 # 本文件
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
# 开发相关
npm start              # 启动开发服务器（实时预览，自动刷新）
npm run clear          # 清除缓存（遇到问题时使用）

# 构建相关（通常不需要手动执行）
npm run build          # 构建生产版本
npm run serve          # 本地预览构建结果

# Git 相关
git add .              # 添加所有更改
git commit -m "消息"   # 提交更改
git push               # 推送到 GitHub（自动触发部署）
```

## ❓ 常见问题

### Q: 每次修改文章都要 build 吗？
**A:** 不需要！
- **本地开发**：运行 `npm start`，修改后自动刷新，无需 build
- **发布到网站**：直接 `git push`，GitHub Actions 会自动 build 和部署

### Q: 如何查看文章效果？
**A:**
- **本地查看**：`npm start` 后访问 `http://localhost:3000/lanbitou/`
- **线上查看**：`git push` 后等待 2-5 分钟，访问 `https://你的用户名.github.io/lanbitou/`

### Q: 马克笔标注不生效？
**A:** 检查语法：
- ✅ 正确：`==文字==`（紧贴，无空格）
- ❌ 错误：`== 文字 ==`（有空格）
- ✅ 正确：`=r=红色==`（颜色标记在开头）
- ❌ 错误：`=r=红色=r=`（结尾应该是双等号）

### Q: 开发服务器启动失败？
**A:**
```bash
npm run clear    # 清除缓存
npm start        # 重新启动
```

## 📚 学习资源

- [Docusaurus 官方文档](https://docusaurus.io/)
- [Markdown 语法指南](https://www.markdownguide.org/)

---

Built with [Docusaurus](https://docusaurus.io/)
