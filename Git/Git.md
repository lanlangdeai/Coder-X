# Git版本管理工具



## 安装

### Linux

```bash
# 1.安装依赖
yum install -y curl-devel expat-devel gettext-devel \
  openssl-devel zlib-devel
# 2.安装git
yum -y install git-core
# 3.查看版本
git --version
git version 1.8.3.1
```







## 使用



### 常用命令

| 命令                                                      | 说明                                               |
| --------------------------------------------------------- | -------------------------------------------------- |
| git remote -v                                             | 查看远程仓库地址                                   |
| git log --pretty=oneline -5                               | 查看历史提交记录(近5条)                            |
| git reset --hard 9b61b7d23412e4e1fe5ebe0580b009fc6e6b6a4b | 指定提交ID强制回退                                 |
| git push origin HEAD --force                              | 将回退内容推送到远端(看场景使用), 需要强制覆盖上去 |
|                                                           |                                                    |
|                                                           |                                                    |
|                                                           |                                                    |
|                                                           |                                                    |
|                                                           |                                                    |
|                                                           |                                                    |
|                                                           |                                                    |











### 相关文件

#### .gitignore

> 放置一些不想添加到版本库中的文件或者目录
>
> 例如: 标识忽略该目录下所有文件但不包含.gitignore文件
>
> - !.gitignore



#### .gitkeep

> 在git中如果是一个空的文件夹是不允许被提交的，可以添加一个.gitkeep的文件作为一个占位符，这样的话这个空文件就可以被提交到版本库中







