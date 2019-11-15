---
title: hexo如何上传图片
abbrlink: d9ac2aad
date: 2017-05-25 20:03:40
---


我之前都是先在CSDN上写好要发布的文章，然后再导出为Markdown文件。然后我就直接将文件复制到_post文件夹下，就行depoly,发布到我的博客网站上，我自己在电脑上浏览是正常的，图片也都能正确的显示出来，但是今天有个评论说不显示图片。我换了手机浏览博客，果然不显示。

解决方法
设置站点配置_config.yml:将post_asset_folder: false改为post_asset_folder: true
安装插件:npm install https://github.com/CodeFalling/hexo-asset-image -- save
运行hexo n "XXXXXX",生成XXXXX.md博文时就会在/source/_posts目录下生成XXXXXX的文件夹，将你想在XXXXX博文中插入的照片放置到这个同名文件夹中即可，图片的命名随意。
添加图片:在想添加的位置写入![](图片名字.图片格式),例如![](1.png)。
