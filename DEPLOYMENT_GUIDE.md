# 部署指南 - 将申论学习站点部署到 GitHub Pages

本指南将帮助你一步步将 Docusaurus 站点部署到 GitHub Pages。

## 📋 前提条件

- 已安装 Git
- 拥有 GitHub 账号
- 已完成项目的本地配置

## 🔧 第一步：修改配置文件

打开 `lanbitou/docusaurus.config.js`，找到并修改以下配置：

```javascript
// 将 YOUR_GITHUB_USERNAME 替换为你的 GitHub 用户名
url: 'https://YOUR_GITHUB_USERNAME.github.io',
baseUrl: '/lanbitou/',
organizationName: 'YOUR_GITHUB_USERNAME',
projectName: 'lanbitou',
```

**示例**：如果你的 GitHub 用户名是 `zhangsan`，则修改为：

```javascript
url: 'https://zhangsan.github.io',
baseUrl: '/lanbitou/',
organizationName: 'zhangsan',
projectName: 'lanbitou',
```

同时修改以下位置的 GitHub 链接：
- `editUrl` 配置（docs 和 blog 部分）
- `navbar` 中的 GitHub 链接
- `footer` 中的 GitHub 链接

## 🌐 第二步：在 GitHub 创建仓库

1. 登录 GitHub
2. 点击右上角的 "+" 号，选择 "New repository"
3. 仓库名称填写：`lanbitou`
4. 选择 "Public"（公开仓库才能使用免费的 GitHub Pages）
5. **不要**勾选 "Initialize this repository with a README"
6. 点击 "Create repository"

## 💻 第三步：推送代码到 GitHub

在项目根目录（`d:\AppDev\lanbitou`）打开终端，执行以下命令：

### 1. 初始化 Git 仓库（如果还没有初始化）

```bash
git init
```

### 2. 添加所有文件

```bash
git add .
```

### 3. 创建第一次提交

```bash
git commit -m "Initial commit: 申论学习站点"
```

### 4. 设置主分支名称

```bash
git branch -M main
```

### 5. 添加远程仓库

将 `YOUR_GITHUB_USERNAME` 替换为你的 GitHub 用户名：

```bash
git remote add origin https://github.com/YOUR_GITHUB_USERNAME/lanbitou.git
```

### 6. 推送到 GitHub

```bash
git push -u origin main
```

如果是第一次推送，可能需要输入 GitHub 用户名和密码（或 Personal Access Token）。

## ⚙️ 第四步：配置 GitHub Pages

1. 打开你的 GitHub 仓库页面：`https://github.com/YOUR_GITHUB_USERNAME/lanbitou`
2. 点击仓库顶部的 "Settings"（设置）
3. 在左侧菜单中找到并点击 "Pages"
4. 在 "Build and deployment" 部分：
   - **Source** 选择：`GitHub Actions`
5. 保存设置

## 🚀 第五步：等待自动部署

1. 点击仓库顶部的 "Actions" 标签
2. 你会看到一个名为 "Deploy to GitHub Pages" 的工作流正在运行
3. 等待工作流完成（通常需要 2-5 分钟）
4. 如果出现绿色的勾号 ✓，说明部署成功

## 🎉 第六步：访问你的站点

部署成功后，访问：

```
https://YOUR_GITHUB_USERNAME.github.io/lanbitou/
```

例如，如果你的用户名是 `zhangsan`，则访问：
```
https://zhangsan.github.io/lanbitou/
```

## 🔄 后续更新

每次修改内容后，只需执行以下命令即可自动重新部署：

```bash
git add .
git commit -m "更新内容描述"
git push
```

GitHub Actions 会自动检测到推送并重新部署站点。

## ❓ 常见问题

### 1. 部署失败怎么办？

- 检查 Actions 标签页中的错误日志
- 确认 `docusaurus.config.js` 中的配置是否正确
- 确认 GitHub Pages 设置中选择了 "GitHub Actions"

### 2. 页面显示 404

- 检查 `baseUrl` 配置是否为 `/lanbitou/`
- 确认仓库名称是否为 `lanbitou`
- 等待几分钟，GitHub Pages 可能需要时间生效

### 3. 样式丢失或资源加载失败

- 检查 `url` 和 `baseUrl` 配置是否正确
- 清除浏览器缓存后重试

### 4. 如何使用自定义域名？

1. 在仓库的 `static` 目录下创建 `CNAME` 文件
2. 文件内容填写你的域名，如：`blog.example.com`
3. 在域名服务商处添加 CNAME 记录指向 `YOUR_GITHUB_USERNAME.github.io`

## 📝 提示

- 建议在本地测试通过后再推送到 GitHub
- 使用 `npm run build` 在本地构建，确保没有错误
- 定期备份重要内容

---

祝你使用愉快！如有问题，请查阅 [Docusaurus 官方文档](https://docusaurus.io/docs/deployment#deploying-to-github-pages)。

