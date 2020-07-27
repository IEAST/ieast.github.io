---
title: git部分常用命令
date: 2020-07-21 11:14:33
tags: #git #工具
---
# git部分常用命令

## 第一次使用git仓库
```sh
git init(建立本地git仓库)
git add XXX(添加文件到本地git仓库)
git commit -m "XXXX"(添加commit 信息)
git remote add origin git@github.com:name/project.git (添加github仓库)
$ git push -u origin master (提交代码)
```
## 以后提交
```sh
git add XXX(添加文件到本地git仓库)
git commit -m "XXXX"(添加commit 信息)
git push (提交代码)
```
## 第二仓库
```sh
git remote add name xx@xxx.com:name/project.git (添加第二git仓库， name 自定义)
git remote rm name (删除仓库)
git push name master (提交指定仓库)
```
