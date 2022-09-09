---
title: HEXO搭建博客教程
date: 2022-08-30 15:37:04
updated: 2022-08-30 15:37:04
tags: 
  - hexo
  - github
  - github公钥
  - github token
  - 七牛云
  - 图床
  - 域名
  - 域名解析
  - butterfly
categories:
  - 博客
  - 教程
keywords: "hexo,域名,butterfly,github搭建博客"
description: 本文通过hexo搭建博客，更换为butterfly主题，使用github托管并绑定域名完成个人博客的搭建
cover: 
aplayer: true
---

{% meting "60198" "netease" "song" "autoplay" "volume:0.1"  "mutex:false" "listmaxheight:340px" "preload:auto" "theme:#ad7a86"%}

---

# 一、HEXO本地安装

## 1.安装环境

1. 安装Node.js

2. 安装Git

 >均从网上下载安装即可

---

## 2.安装HEXO

1. 新建一个用于存放hexo的文件夹，如我本地创建了一个 blog 文件夹，并右键--->在终端打开

   > 我这里是示范，此处应该为空文件夹

   ![image-20220830180802469](http://rhbsj8k4s.hd-bkt.clouddn.com/img/image-20220830180802469.png)

2. 在cmd中用npm安装hexo

   ```js
   npm install -g hexo-cli
   ```

   > 若安装进度卡住可以使用淘宝镜像源
   >
   > ```js
   > //  安装淘宝镜像
   > npm install -g cnpm -registry=https://registry.npm.taobao.org
   > 
   > //  检查是否安装
   > cnpm -v
   > 
   > // 使用cnpm安装
   > cnpm install -g hexo-cli
   > ```

3. 安装完成后在cmd中键入hexo查看是否安装成功，若出现以下命令行则为安装成功

   ![image-20220830182748993](http://rhbsj8k4s.hd-bkt.clouddn.com/img/image-20220830182748993.png)

4. 安装完成后，使用初始化命令进行初始化

   ```
   hexo init
   ```

5. 初始化完成后进行静态部署

   ```
   // 清除缓存
   hexo clean
   // 生成文件
   hexo g
   // 部署
   hexo s
   ```

   ---
   
   # 二、主题安装
   
   ##  1. Butter Fly
   
   1. 在项目根目录下执行clone主题
      ```
      git clone -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly
      ```
   
   2. 修改项目的配置文件 _config.yml 中的theme为：butterfly
   
      ![image-20220908171249706](http://rhbsj8k4s.hd-bkt.clouddn.com/img/image-20220908171249706.png)
   
   3. 建议
   
      > 为了将主题配置和站点配置区分开，建议复制一份主题目录下的_config.butterfly.yml到根目录下，此后的主题配置都可以在该配置文件中修改
      >
      > 主题配置可以参考官方文档：https://butterfly.js.org/posts/21cfbf15/
   
      ---
   
      ## 2.其他主题
   
      > 找到对应主题的GitHub仓库，克隆到theme文件夹，在配置里面更改theme主题即可
   
      ---
   
      # 3.GitHub托管部署
   
      ## 1. GitHub配置
   
      1. 新建仓库，仓库名按照下面示范填进自己的用户名
   
         ![image-20220908174847553](http://rhbsj8k4s.hd-bkt.clouddn.com/img/image-20220908174847553.png)
   
      2. 生成token
   
         > ​	1.在个人设置页面找到setting
         >
         > ![image-20220908175148744](http://rhbsj8k4s.hd-bkt.clouddn.com/img/image-20220908175148744.png)
         >
         > 2. 找到developer setting
         >
         >    ![image-20220908175232663](http://rhbsj8k4s.hd-bkt.clouddn.com/img/image-20220908175232663.png)
         >
         >    3. 选择个人访问令牌`Personal access tokens`，然后选中生成令牌`Generate new token` 
         >
         >       ![image-20220908175403029](http://rhbsj8k4s.hd-bkt.clouddn.com/img/image-20220908175403029.png)
         >
         >       4. 设置token的有效期，访问权限等，生成token
         >
         >          ![image-20220908175449453](http://rhbsj8k4s.hd-bkt.clouddn.com/img/image-20220908175449453.png)
         >
         >          5.记得把你的token保存下来，因为你再次刷新网页的时候，你已经没有办法看到它了
   
         ---
   
         ## 2.HEXO配置
   
         1. 配置站点文件_conbfig.yml
   
         ![image-20220908175905199](http://rhbsj8k4s.hd-bkt.clouddn.com/img/image-20220908175905199.png)
   
         2. 安装 `hexo-deployer-git`
   
          ```
            cnpm install --save hexo-deployer-git
          ```
   
         3. 使用`hexo -d` 提交
