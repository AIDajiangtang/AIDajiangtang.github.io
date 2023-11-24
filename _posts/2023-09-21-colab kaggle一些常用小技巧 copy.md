---
published: false
layout: post
title: "0.序"
categories: kaggle colab中的一些常用小技巧
banner:
  video: https://vjs.zencdn.net/v/oceans.mp4
  loop: true
  volume: 0.8
  start_at: 8.5
  image: https://bit.ly/3xTmdUP
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
excerpt: "序"
top: 2

---

**1**
%pwd 查看当前目录
%cd 切换目录

**2**
import os
os.environ['KAGGLE_USERNAME'] = "baomac"
os.environ['KAGGLE_KEY_PATH'] = "/content/kaggle.json"
os.environ['KAGGLE_CONFIG_DIR'] = "/content"

kaggle上Copy API Command
!kaggle datasets download -d abhinavwalia95/entity-annotated-corpus
这样就可以在colab上下载数据了
