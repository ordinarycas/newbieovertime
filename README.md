# 菜加班 - NewbieOvertime

### 網站介紹

一個上班族分享生活、技術的地方，也是一個專門為新手或初學者提供相關資訊和知識的部落格。在這提供各種各樣的教學文章和指南，幫助初學者從基礎開始學習各種領域的技能和知識。目前 Podcast 主要分享自己的工作生活，也順便當週記督促自己。


若有不同想法歡迎分享指點。

該部落格是使用 Jekyll 建置，網站初始樣板 Theme - Mundana by WowThemes.net

### 撰寫說明

文章的檔案名稱結構為 {年份}-{月份}-{日期}-{標題}。

文章範例如下：

```
---
layout: post
title: "Hello, World!"
date: 2022-12-21 12:00:00 +0800
author: John Doe
published: false
categories: [ jekyll, tutorial ]
---

文章內文開始

```

### 本機環境執行

先安裝 Ruby 若想在 Windows 環境下安裝 Ruby Version Manager(RVM) 只能透過 Windows Subsystem for Linux(WSL)，安裝完 Ruby 後可執行下面指令，安裝 bundler 跟 jekyll

```
gem install bundler jekyll
```

Bundler是用來解決管理Gems相依性問題。簡單來說，因為同一個套件會有很多個版本，所以在使用上就會有套件多版本管理上的問題，而Bundler則是解決這個問題的套件。
```
bundle install
```

```
bundle exec jekyll serve --watch --drafts
```

### Copyright

Copyright (C) 2023 [newbieovertime.work](newbieovertime.work).
