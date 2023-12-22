---
date : 2023-07-21
tags : Productivity PicGo
---
---
## 寫 Markdown 的痛苦，圖片管理很麻煩

至從開始使用 Markdown 寫筆記後，我發現一個麻煩的問題就是圖片管理。

在 Markdown 筆記工具插入圖片，實際上都是插入一段 Markdown 的圖片語法 `![](圖片 url)` 。若是直接將圖片拖曳到筆記工具中，通常都是顯示 `![](圖片在自己電腦中的路徑)` ，這代表換了一台電腦、或是將 Markdown 筆記分享給其他人時，這張圖片就顯示不出來了

<br>

## PicGo 操作步驟
**Step.1 下載 PicGo**
首先先到 PicGo 開發者的 Github 下載安裝檔

[Releases · Molunerfinn/PicGo (github.com)](https://github.com/Molunerfinn/picgo/releases)

**Step.2 安裝**

**Step.3 設定介面 (以 Mac 舉例)**
PicGo 在 Mac 中預設是在上方工具列，右鍵點擊 PicGo 圖示後選擇「打開詳細窗口」進行設定

**Step.4 點擊「圖床設置」，使用 Github 作為圖床**

![screenshot 2023-07-21 at 6.30.11 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202023-07-21%20at%206.30.11%20PM.jpg)

**Step.5 取得 Github Token**
![[取得Github帳號Token]]

**Step.6 設定 URL 格式**
為了讓圖片上傳後回傳的 URL 格式更符合我們需要，我們可以客製化連結格式
點擊「PicGo設置」>「自定義連結格式」，可修改上傳完圖片後的返回 url 格式，我個人設定成 `![$fileName]($url)` 

[$fileName] = 圖片名稱

[$url] = 圖片網址

設定完成後，記得到「上傳區」> 點擊「Custom」，這樣連結就會以`![圖片名稱](url)` 複製到剪貼簿上

## Ref
[寫 Markdown 的好夥伴！PicGo 支援快速上傳圖片到預設圖床，並且返回 Markdown 圖片超連結 | by 朱騏 | PM的生產力工具箱 | Medium](https://medium.com/pm%E7%9A%84%E7%94%9F%E7%94%A2%E5%8A%9B%E5%B7%A5%E5%85%B7%E7%AE%B1/%E5%AF%AB-markdown-%E7%9A%84%E5%A5%BD%E5%A4%A5%E4%BC%B4-picgo-%E6%94%AF%E6%8F%B4%E5%BF%AB%E9%80%9F%E4%B8%8A%E5%82%B3%E5%9C%96%E7%89%87%E5%88%B0%E9%A0%90%E8%A8%AD%E5%9C%96%E5%BA%8A-%E4%B8%A6%E4%B8%94%E8%BF%94%E5%9B%9E-markdown-%E5%9C%96%E7%89%87%E6%A0%BC%E5%BC%8F-7b83ad56ddb7)