---
title: Hexo安装
date: 2023-10-10 21:00:00
tags:
  - 博客
---

# hexo安装流程

## 主题安装
> https://github.com/SumiMakito/hexo-theme-typography

### 进入根目录
``` bash
cd hexo
```

### 安装依赖项
``` bash
npm uninstall --save hexo-generator-category # 此处我们使用 hexo-generator-category-enhance
npm install --save hexo-renderer-pug hexo-generator-archive hexo-generator-category-enhance hexo-generator-feed hexo-generator-tag
npm install --save hexo-prism-plugin # 语法高亮支持
```

### 安装主题
``` bash
cd themes
git clone https://ghproxy.com/https://github.com/SumiMakito/hexo-theme-typography # 这里使用ghproxy 加快github速度
mv hexo-theme-typography typography
npm install
```

### 修改配置文件
对根目录下的主配置文件 _config.yml 进行响应的改动
``` yml
theme: typography

highlight:
  enable: false # we will use the prism plugin instead

plugin:
  - hexo-generator-category-enhance
  - hexo-generator-feed
  - hexo-asset-image
  - hexo-prism-plugin
  - hexo-toc
  # ... other plugins you'd like to enable

# Generate archive page
archive_generator:
  per_page: 0

# Generate categories index page and each category page
category_generator:
  per_page: 10
  enable_index_page: true

# Generate tags index page and each tag page
tag_generator:
  per_page: 10
  enable_index_page: true

# Generator atom feed for you website
feed:
  type: atom
  path: atom.xml
  limit: 20
  hub:
  content:
  content_limit: 140
  content_limit_delim: ' '

# For syntax highlighting
prism_plugin:
  mode: 'preprocess'
  theme: 'default'
  line_number: true 
```
