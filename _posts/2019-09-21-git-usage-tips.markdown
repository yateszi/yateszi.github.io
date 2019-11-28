---
layout: post
title: "git 基本用法"
data: 2019年 09月 21日 星期六 11:28:36 CST
categories: jekyll update
---
## 基本用法
1. 从版本库中检出/克隆
`git clone xxx.git`
2. 添加文件到版本控制
`git add file/directory`
3. 提交到本地库
`git commit -m"msg"`
4. 推送到远端库
`git push origin master`

## 使用gvimdiff替代git自带diff工具
```shell
git config --global diff.tool gvimdiff
git config --global difftool.prompt false
git config --global alias.d difftool
```
设置difftool 为gvimdiff，同时增加缩写快捷键 d->difftool
用法如下
```
git d filetodiff
```

