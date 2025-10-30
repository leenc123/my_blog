# Git命令整理
## 添加原仓库作为上游远程仓库（便于后续同步更新）
```git remote add upstream https://github.com/原作者/原仓库名.git```
## 验证远程仓库配置
```git remote -v ```     
## 首先获取上游仓库的最新更改
```git fetch upstream```
## 基于上游的main分支创建新分支
```git checkout -b feature/你的功能描述 upstream/main```
## 或者基于上游的develop分支
```git checkout -b feature/你的功能描述 upstream/develop```
## 需要显式设置推送到你的fork仓库
```git push -u origin feature/chat-integration```