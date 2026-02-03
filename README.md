# 中大评课社区 (SYSU Course Rating) 🎓

一个基于 GitHub API 构建的无后端课程评价系统。所有数据直接存储在 GitHub 仓库中，无需服务器，永久免费且开源。

## ✨ 功能特性

- **完全无后端 (Serverless)**: 利用 GitHub Repository Contents API 作为数据库。
- **即时响应**: 课程添加与评价提交后，本地立即更新，并自动同步至云端。
- **匿名访问**: 内置公用 Token，访客无需登录即可浏览和评价。
- **管理员模式**: 只有仓库创建者（持有 Admin Token）可以删除违规课程或恶意评价。
- **极简部署**: 纯静态页面，一键部署至 GitHub Pages。

## 🛠️ 技术栈

- **前端框架**: React + Vite
- **UI 库**: Tailwind CSS + Lucide React
- **数据存储**: GitHub Repository Contents API (JSON Files)

## 🚀 快速开始

### 1. 本地运行

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev
```

打开浏览器访问 `http://localhost:5173`。

### 2. 部署到 GitHub Pages

项目已配置好自动化部署脚本。

```bash
npm run deploy
```

该命令会自动构建项目并将 `dist` 目录推送至远程仓库的 `gh-pages` 分支。

## 📖 数据存储说明

本项目采用 **"文件即数据库"** 的设计模式以解决 GitHub Search API 的索引延迟问题。

- 所有课程数据存储在仓库的 `/data/courses/` 目录下。
- 每个课程对应一个 JSON 文件 (例如 `170658.json`)。
- 当用户评价时，前端会通过 GitHub API 更新对应的 JSON 文件。

## 🛡️ 管理员功能

为了防止滥用，删除功能设有权限控制：

1. 点击对应的 "🔒" 图标。
2. 输入拥有该仓库 Write/Admin 权限的 **GitHub Personal Access Token**。
3. 验证通过后，课程卡片和评论区会出现删除按钮 (🗑️)。

## 🤝 贡献

欢迎提交 Issue 或 Pull Request 来改进这个项目！

## 📄 开源协议

MIT
