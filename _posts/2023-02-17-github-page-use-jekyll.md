---
layout: post
title:  "使用 Jekyll 在 GitHub 建立部落格"
author: jhan
categories: [Jekyll]
image: https://picsum.photos/750/500
tags: [Jekyll, GitHub]
---

之前就有使用 [GitHub][GitHub] 平台建立部落格過了，那時是使用 [Hexo][Hexo] 但因為 [Hexo][Hexo] 需要在本地建立環境再將寫好的文章生成為靜態頁面，對於一個沒有立即環境的使用者或寫者都非常不方便；再評估目的後在2022年嘗試使用 Amazon Web Services (AWS)、Google Cloud Platform (GCP)、[DigitalOcean]雲端平台建立 Wordpress 網站，但由於費用太貴且無上限，尤其在 AWS 更是讓我破費快 200USD，但也是自己不小心開啟了 Transfer Family 服務才會破費這麼多。

## 回歸 GitHub

經歷了以上教訓還是回歸到 [GitHub][GitHub] 建立部落格，但服務也不是免費給你以下是 GitHub Page 使用限制節錄部分

* GitHub Pages 提供 1GB 的空間，每月提供最高 100GB 的流量。
* 使用 [Jekyll][Jekyll] 建立 GitHub Pages 最高十次產生靜態文件，自訂 GitHub Actions 除外。
* 在網站高峰的時候會出現 HTTP 狀態碼 Code 429, Too Many Requests 頁面。

因為 GitHub Pages 支援 [Jekyll][Jekyll] 自動生成靜態文件所以就選擇 [Jekyll][Jekyll]，我這邊也列出其他靜態頁面產生器的比較(表一)。

| 比較             | Jekyll            | Hexo                 | Hugo                 |
| ---------------- | ----------------- | -------------------- | -------------------- |
| 程式語言         | Ruby              | EJS                  | Go                   |
| 生成速度(三者比) | 慢                | 中                   | 快                   |
| 生成方式         | GitHub Pages 幫轉 | 本地或GitHub Actions | 本地或GitHub Actions |

<p class="text-center">(表一，靜態頁面產生器)</p>

對於本地(機)環境有限制的使用者，我個人是推薦 [Jekyll] 這個靜態頁面產生器，若沒有的話可以使用 [Hugo] 因為個人認為 Go 是為來的趨勢，[Hexo] 的話我之前在寫前端 JavaScript 的時候有使用它來試做一個 Bloger 但也因本地環境的關係就打消這個念頭了。

### 開始架設 Jekyll

在使用 Jekyll 前要先安裝 [Ruby] 環境，安裝方式在官網都有說明，筆者這邊是使用 Windows 的環境所以只要下載 RubyInstaller 按照安裝流程點擊下一步就可以了。類 Unix 系統可以先安裝 Ruby Version Manager (RVM，Ruby版本管理器)。

#### Ruby 透過 RVM 安裝 for 類 Unix

```bash
gpg --keyserver keyserver.ubuntu.com --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

# rvm 安裝選項
\curl -sSL https://get.rvm.io | bash -s stable    # 安裝穩定版本
\curl -sSL https://get.rvm.io | bash              # 安裝最新版本

# 測試 rvm 是否安裝成功
type rvm | head -n 1                              # 成功的話會回傳 RVM is a shell function

# rvm 更新或重新安裝（按照上面的步驟重新執行一次安裝程式是可以的，或者可以透過下面的方式更新）
rvm cleanup all         # 刪除安裝的所有 Ruby 版本和相關的資源
rvm get stable          # 取得穩定版
rvm get master          # 取得最新版

# 安裝 Ruby
rvm list known                # 檢視所有 RVM 中的 Ruby 版本
rvm install 3.2.1             # 安裝特定版本的 Ruby
rvm use 3.2.1                 # 使用特定版本的 Ruby

# 檢查是否安裝成功
ruby -v
# 會顯示「ruby 3.2.1 (2023-02-08 revision 31819e82c8) [x86_64-linux]」
```

#### Ruby 安裝 Jekyll

```bash
gem install bundler jekyll

# 建立新部落格，會自動建立「my-awesome-site」資料夾將專案放置在裡面
jekyll new my-awesome-site

# 移動至專案目錄
cd my-awesome-site

# 運行 jekyll 網站服務
bundle exec jekyll serve
```

#### 部屬在 GitHub Page 上

新增一個空 Repository ，將專案 Push 上去，在 Repository 設定中選擇 GitHub Page 過5至10分鐘網站就會得到你的部落格了。

<p class="mb-0">參考資料</p>
GitHub Page 使用限制 (February 17, 2023). [https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#usage-limits](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages#usage-limits)


[DigitalOcean]:https://m.do.co/c/5d50dc9fa138
[GitHub]:https://github.com/
[Hexo]:https://github.com/hexojs/hexo
[Hugo]:https://github.com/gohugoio/hugo
[Jekyll]:https://github.com/jekyll/jekyll
[Ruby]:https://www.ruby-lang.org/zh_tw/downloads/