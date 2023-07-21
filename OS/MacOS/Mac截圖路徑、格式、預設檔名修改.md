---
date : 2023-07-21
tags : MacOS
---
---
## 在 Mac 上拍攝螢幕快照
- 全螢幕截圖＝ Command（⌘）+ shift + 3
- 所選範圍截圖＝ Command（⌘）+ shift + 4
- 視窗截圖＝ Command（⌘）+ shift + 4 + 空白鍵
- 去除陰影截圖＝ Command（⌘）+ shift + 4 + 空白鍵 + option

<br>

## 修改截圖路徑
打開終端機，在 `location` 後填上路徑
```
defaults write com.apple.screencapture location ~/Desktop/Screenshot
```

<br>

## 修改截圖格式
打開終端機，在 `type` 後填上檔案格式，支援 jpg 、 gif 、bmp 、pdf 、png 及 tiff 格式
```
defaults write com.apple.screencapture type jpg
```
<br>

## 修改截圖名稱
打開終端機，在