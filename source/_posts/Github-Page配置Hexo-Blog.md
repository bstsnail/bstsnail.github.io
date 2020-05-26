---
title: Github Page配置Hexo Blog
date: 2020-05-26 22:16:15
tags: setup
---

1. 安装Hexo
   ```
   npm install hexo-cli -g
   ```
2. 安装deploy插件
   ```
   npm install hexo-deployer-git --save
   ```
3. 初始化blog
   ```
   hexo init blog
   ```
4. 测试hexo
   ```
   cd blog
   npm install
   hexo g
   hexo s
   ```
   浏览器中打开http://localhost:40000
5. 下载Next主题
   ```
   git clone https://github.com/theme-next/hexo-theme-next themes/next
   ```
6. 配置主题
   ```
   a. 修改 _config.xml
     设置
      -- title: Bstsnail's Notes
      -- subtitle: Quite Notes
      -- theme: next
      -- language: zh-Hans
      -- deploy:
           type: git
           repository: https://github.com/bstsnail/bstsnail.github.io.git
           branch: master
   b. 修改 themes/next/_config.xml
     设置
      -- auto_excerpt:
         enable: true
         length: 300 (超过300个字就自动截断)
      -- scheme: Pisces
   ```
7. 添加搜索功能
   引用于[搜索服务](http://theme-next.iissnan.com/third-party-services.html#search-system)的Local Search
   ```
   a. 在站点根目录安装generator-searchdb
      npm install hexo-generator-searchdb --save
   b. 配置站点_config.xml
      search:
        path: search.xml
        field: post
        format: html
        limit: 10000
   c. 主题配置文件themes/next/_config.xml启用搜索功能
      local_search:
        enable: true
   ```
8. 设置tags
   ```
   hexo new page "tags"
   ```
   并编辑source/tags/index.md文件
   ```
   ---
   title: tags
   date: 2020-05-26 23:13:06
   type: "tags"
   ---
   ```
9. 安装deployer
   ```
   npm i hexo-deployer-git
   ```
10. 部署到bstsnail.github.io
   ```
   hexo g
   hexo d
   ```
   浏览器直接访问bstsnail.github.io
11. 把源文件存放到bstsnail.github.io这个代码库的其他分支

