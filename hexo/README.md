# 默认话题

## 🧑‍💻 User

hexo搭建个人博客平台

---
## 🤖 Assistant

我来为你详细介绍如何使用 Hexo 搭建个人博客平台：

## 🚀 一、环境准备

### 1. 安装 Node.js
- 访问 [Node.js 官网](https://nodejs.org/) 下载安装
- 验证安装：
```bash
node -v
npm -v
```

### 2. 安装 Git
- Windows: [Git for Windows](https://gitforwindows.org/)
- Mac: `brew install git`
- Linux: `sudo apt-get install git`

## 📦 二、安装 Hexo

```bash
# 全局安装 Hexo CLI
npm install -g hexo-cli

# 验证安装
hexo -v
```

## 🎯 三、创建博客项目

```bash
# 初始化博客
hexo init my-blog
cd my-blog

# 安装依赖
npm install

# 本地预览
hexo server
# 访问 http://localhost:4000
```

## 🎨 四、常用命令

```bash
# 创建新文章
hexo new "文章标题"

# 生成静态文件
hexo generate  # 或 hexo g

# 启动本地服务器
hexo server    # 或 hexo s

# 部署到服务器
hexo deploy    # 或 hexo d

# 清理缓存
hexo clean
```

## 🌈 五、主题配置

### 1. 安装主题（以 Butterfly 为例）
```bash
cd my-blog
npm install hexo-theme-butterfly
```

### 2. 修改配置文件 `_config.yml`
```yaml
# 站点配置
title: 你的博客名称
subtitle: 副标题
description: 博客描述
keywords: 关键词
author: 你的名字
language: zh-CN
timezone: Asia/Shanghai

# URL
url: https://yourdomain.com
permalink: :year/:month/:day/:title/

# 主题
theme: butterfly

# 部署
deploy:
  type: git
  repo: https://github.com/username/username.github.io.git
  branch: main
```

## 📝 六、写作指南

### 文章 Front-matter 示例：
```markdown
---
title: 文章标题
date: 2024-01-01 12:00:00
tags: [标签1, 标签2]
categories: 分类
cover: /images/cover.jpg
---
```

### 文章内容使用 Markdown 语法：
```markdown
# 一级标题
## 二级标题

**粗体** *斜体*

- 列表项1
- 列表项2

[链接文字](URL)

![图片描述](图片URL)

> 引用内容

`行内代码`

```代码块
```

## 🌐 七、部署到 GitHub Pages

### 1. 安装部署插件
```bash
npm install hexo-deployer-git --save
```

### 2. 创建 GitHub 仓库
- 仓库名格式：`username.github.io`
- 设置为公开仓库

### 3. 配置部署信息
```yaml
# _config.yml
deploy:
  type: git
  repo: https://github.com/username/username.github.io.git
  branch: main
  message: "更新博客"
```

### 4. 部署
```bash
hexo clean
hexo generate
hexo deploy
```

## 🔧 八、实用插件推荐

```bash
# 文章搜索
npm install hexo-generator-search

# RSS 订阅
npm install hexo-generator-feed

# 站点地图
npm install hexo-generator-sitemap

# 图片处理
npm install hexo-asset-image

# 字数统计
npm install hexo-wordcount
```

## 🎯 九、优化建议

### 1. 性能优化
- 使用 CDN 加速静态资源
- 压缩图片
- 启用 Gzip 压缩

### 2. SEO 优化
- 配置站点地图
- 添加 robots.txt
- 优化 meta 标签
- 使用结构化数据

### 3. 内容管理
- 定期备份
- 使用标签和分类
- 添加评论系统（如 Gitalk、Valine）

## 💡 十、常见问题

### Q1: 本地预览正常，部署后样式丢失？
A: 检查 `_config.yml` 中的 `url` 配置是否正确

### Q2: 如何添加自定义域名？
1. 在域名服务商添加 CNAME 记录
2. 在博客 `source` 目录创建 `CNAME` 文件
3. 文件内容：`yourdomain.com`

### Q3: 如何备份博客？
```bash
# 备份源文件
git init
git add .
git commit -m "备份"
git remote add origin your-repo-url
git push -u origin main
```

## 📚 学习资源

- [Hexo 官方文档](https://hexo.io/zh-cn/docs/)
- [Butterfly 主题文档](https://butterfly.js.org/)
- [Markdown 语法指南](https://www.markdownguide.org/)

这样你就拥有了一个功能完整的个人博客平台！可以根据自己的需求进一步定制主题和功能。
