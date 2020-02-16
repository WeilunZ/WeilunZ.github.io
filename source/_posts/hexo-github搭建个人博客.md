---
title: hexo + github搭建个人博客
date: 2019-09-14 20:40:25
tags: blog
---
####  步骤

* 安装Node.js
* 添加国内镜像源
`npm config set registry https://registry.npm.taobao.org`
* 安装git
* 注册Github账号，并新建仓库`xxx.github.io`，其中`xxx`为你的Github用户名，随后在仓库Settings按钮点击后，往下拉可以看到Github Pages，点击链接后可以看到自己网页
* 安装Hexo
`npm i hexo-cli -g`
`hexo -v`
`npm i hexo-deployer-git`
* blog初始化
`hexo init`初始化文件夹
`npm install`安装必备组件
* 安装插件
参考 https://github.com/blleng/hexo-theme-lx
* 修改配置
项目根目录下_config.yml文件中，修改最后一行的配置
```yaml
deploy:
  type: git
  repository: https://github.com/WeilunZ/WeilunZ.github.io
  branch: master
```
* hexo命令三部曲
`hexo g`生成静态网页
`hexo s`运行本地服务器
`hexo d`上传至github

* 增加一个新文章
在项目目录下`hexo new post "hexo博客搭建"`，双引号内的为文章的title。

---
ps: 更多细节可以参考 https://zhuanlan.zhihu.com/p/35668237
