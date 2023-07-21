---
date : 2023-07-21
tags : MacOS
---
---
> 為了避免您修改或誤刪重要檔案導致 Mac 系統損壞的情況出現，蘋果會隱藏它認為重要的檔案和資料夾，如「資源庫」

## 透過「快捷鍵」在 Mac 顯示隱藏檔案和資料夾
使用快捷鍵 `Shift + Command + .`。在 Finder 中按一次快捷鍵以顯示所有隱藏檔案和資料夾，再按一次以隱藏它們
![screenshot 2023-07-21 at 6.48.38 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202023-07-21%20at%206.48.38%20PM.jpg)

<br>

## 透過「終端機」在 Mac 顯示隱藏檔案和資料夾
使用快捷鍵的方式只能暫時顯示隱藏檔案。要永久顯示它們，可使用「終端機」

**Step.1** 開啟終端機

**Step.2** 輸入：
```
defaults write com.apple.finder AppleShowAllFiles TRUE
```

**Step.3** 繼續輸入：
```
killall Finder
```