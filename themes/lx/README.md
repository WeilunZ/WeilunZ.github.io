# Hexo-Theme-Lx

[![Github Release](https://img.shields.io/github/release/blleng/hexo-theme-lx.svg)](https://github.com/blleng/hexo-theme-lx/releases/)
[![Github License](https://img.shields.io/github/license/blleng/hexo-theme-lx.svg)](https://github.com/blleng/hexo-theme-lx/blob/master/LICENSE)
[![HitCount](http://hits.dwyl.io/blleng/hexo-theme-lx.svg)](http://hits.dwyl.io/blleng/hexo-theme-lx)

>尚在开发中。归档、分类 、标签页面还有待完善。
>...
>欢迎Fork，欢迎Clone，不拒绝Star

Demo:[https://lx.blleng.cn](https://lx.blleng.cn)

## 示例

![demo](demo/demo.jpg)

## 使用：

在博客根目录:

```bash
$ git clone https://github.com/blleng/hexo-theme-lx themes/lx
```

更改站点设置文件`_config.yml`:

```yml
theme: lx
```

## 最近更新

调整了`css`的结构(V1.4.5)

修复了一些已知问题（V1.3.5）

本地搜素(V1.3.4)

页面布局优化(V1.2.4)

社交媒体链接(V1.2.4) 

## 功能配置

>这里的说明并不完整，请参考`themes/lx/_config.yml`中的注释信息。

### 统计

引入了百度统计和谷歌统计。

启用：在`themes/lx/_config.yml`填写:

```yml
google_analytics: ... ##谷歌统计ID
baidu_analytics: ... ##百度统计ID
```

### 本地搜索

先下载插件`hexo-generator-searchdb`:

```bash
$ npm install hexo-generator-searchdb -s
```

在`themes/lx/_config.yml`中配置:

```yml
local_search:
  enable: true
```

更多配置详见`themes/lx/_config.yml`。

### 评论

评论使用valine，官网：[https://valine.js.org](https://valine.js.org)

启用：在`themes/lx/_config.yml`填写:

```yml
comment:
  enable: true # true:启用 | false:停用
  appid: ... #leancloud appid
  appkey: ... #leancloud appkey
  notify: false
  verify: false
  placeholder: 此处留言 #评论框文字
  avatar: identicon #游客默认头像
  guest_info: nick,mail,link #评论时需填写的内容（均为选填）
  pageSize: 10 #一次性展示的评论数
  language: zh-cn
```

在文章头填入`comment: true`即可在该页面启用评论:

```markdown
---
date: ...
title: ...
categories: ...
tags: ...
comment: true //启用评论
mathjax: ...
---
```

`appid`和`appkey`在leancloud创建应用后即可获取。

### Social Links

社交媒体链接，在`themes/lx/_config.yml`配置:

```yml
social:
  enable: true
  links:
    #Github: ... #去除开头的'#'注释符，填写链接即可
```

### Mathjax

支持数学公式和化学方程式。

启用：在`themes/lx/_config.yml`填写:

```yml
mathjax:
  enable: true  ##true:启用 | false:停用
  cdn: //cdn.bootcss.com/mathjax/2.7.5/latest.js?config=TeX-MML-AM_SVG  ##为保证输出效果，选择SVG格式输出。
```

在文章头填入`mathjax: true`即可在该页面启用评论:

```markdown
---
date: ...
title: ...
categories: ...
tags: ...
comment: ...
mathjax: true //启用Mathjax
---
```

## 文章写作样式

### 文章摘要

在`<!--more-->`标签之前的内容将作为文章摘要在首页展示。

### Note tag

可选用`default`、`info`、`primary`、`success`、`warning`、`danger`。

示例：

```markdown
{%note default%}
### title
content
{%endnote%}
```

### Label tag

可选用`default`、`info`、`primary`、`success`、`warning`、`danger`。

示例：

```markdown
{%label default@content%}
```

### Button tag

标准样式：

```markdown
{%btn url,content,hand-o-right fa-fw,title%}
```

说明：

`url`：指向的链接

`content`：内容

`hand-o-right fa-fw`：图标，可换成其他图标。`fa-fw`：fix width

`title`：title

### center-quote tag

示例：

```markdown
{%cq%}
人类的悲欢并不相通，我只觉得他们吵闹。<br><strong>——鲁迅</strong>
{%endcq%}
```

### video tag

示例：

```markdown
{% video url %}
```

说明：

`url`：视频链接
