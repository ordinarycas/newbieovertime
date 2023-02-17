---
layout: post
title:  "使用 Jekyll 在 GitHub 建立部落格"
author: jhan
categories: [Jekyll]
image: https://picsum.photos/750/500
tags: [Jekyll, GitHub]
---

之前就有使用 [GitHub][GitHub] 平台建立部落格過了，那時是使用 [Hexo][Hexo] 但因為 [Hexo][Hexo] 需要在本地建立環境再將寫好的文章生成為靜態頁面，對於一個沒有立即環境的使用者或寫者都非常不方便；再評估目的後在2022年嘗試使用 Amazon Web Services (AWS)、Google Cloud Platform (GCP)、[DigitalOcean] 雲端平台建立 Wordpress 網站，但由於費用太貴且無上限，尤其在 AWS 更是讓我破費快 200USD，但也是自己不小心開啟了 Transfer Family 服務才會破費這麼多。

## 回歸 GitHub

經歷了以上教訓還是回歸到 [GitHub][GitHub] 建立部落格，但服務也不是免費給你以下是 GitHub Page 使用限制節錄部分

* GitHub Pages 提供 1GB 的空間，每月提供最高 100GB 的流量。
* 使用 [Jekyll][Jekyll] 建立 GitHub Pages 最高十次產生靜態文件，自訂 GitHub Actions 除外。
* 在網站高峰的時候會出現 HTTP 狀態碼 Code 429, Too Many Requests 頁面。

因為 GitHub Pages 支援 [Jekyll][Jekyll] 自動生成靜態文件所以就選擇 [Jekyll][Jekyll]，我這邊也列出其他靜態頁面產生器。

| 比較             | Jekyll            | Hexo                 | Hugo                 |
| ---------------- | ----------------- | -------------------- | -------------------- |
| 程式語言         | Ruby              | EJS                  | Go                   |
| 生成速度(三者比) | 慢                | 中                   | 快                   |
| 生成方式         | GitHub Pages 幫轉 | 本地或GitHub Actions | 本地或GitHub Actions |



<p class="mb-0">參考資料</p>
GitHub Page 使用限制 (February 17, 2023). [https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#usage-limits](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#usage-limits)


[DigitalOcean]:https://m.do.co/c/5d50dc9fa138
[GitHub]:https://github.com/
[Hexo]:https://github.com/hexojs/hexo
[Hugo]:https://github.com/gohugoio/hugo
[Jekyll]:https://github.com/jekyll/jekyll