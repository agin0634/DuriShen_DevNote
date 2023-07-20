---
date : 2023-07-18 11:50
tags : flutter app
---

## 安裝 Flutter SDK

[Flutter SDK archive | Flutter](https://docs.flutter.dev/release/archive?tab=windows#windows)

建議用 git 安裝 master channel
```
git clone -b master https://github.com/flutter/flutter.git
```

解壓縮後將 flutter 內的 bin 資料夾路徑加到環境變數 `Path` 內
![Pasted image 20230718235838](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/Pasted%20image%2020230718235838.png?token=AGFDTPZPFHKLRHLIJKTGNQTEXF336)
![[Pasted image 20230718235854.png || 500x500]]

<br>

## 安裝 Android Studio

透過 `flutter doctor` 來診斷環境，由顯示的訊息可知我們還需安裝 Android SDK 和 Android Studio
![[Pasted image 20230719000020.png]]
[Download Android Studio & App Tools - Android Developers](https://developer.android.com/studio?gclid=Cj0KCQiAjJOQBhCkARIsAEKMtO3zEhdK4_I0CEZic3UH4dl-9gVXuHFR9dCl3TOHKjmv3xWLU3UxfhYaApfAEALw_wcB&gclsrc=aw.ds)

安裝完 Android SDK 和 Android Studio 後，新增環境變數 ANDROID_HOME，並將變數值設定為 SDK 存放路徑
![[Pasted image 20230719000127.png]]

再透過 flutter doctor --android -licenses 指令同意一些授權
![[Pasted image 20230719000152.png]]

再到 Android Studio>Plugins 安裝 Flutter ，同時還會安裝 Dart
![Pasted image 20230719000217](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/ImagesPasted%20image%2020230719000217.png?token=AGFDTP77YSW2HULXILYQF73EXF22C)

<br>

## Visual Studio Code 設定
啟動 VS Code ，點選擴充功能並安裝 `Flutter` 和 `Android iOS Emulator` ， Dart 會和 Flutter 同時被安裝
![[Pasted image 20230719000304.png]]