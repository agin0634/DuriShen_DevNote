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
![Pasted image 202307ff1823h5838](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/Pasted%20image%20202307ff1823h5838.png?token=AGFDTPZSS4HJP5P77FVHIL3EXGDVO)
![Pasted image 2023071823585f4](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/Pasted%20image%202023071823585f4.png?token=AGFDTP53DM55EY52EUBC5DLEXF4JM)

<br>

## 安裝 Android Studio

透過 `flutter doctor` 來診斷環境，由顯示的訊息可知我們還需安裝 Android SDK 和 Android Studio
![Pasted image 20230719000020](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/Pasted%20image%2020230719000020.png?token=AGFDTP2DYTMKBP52RWUD5U3EXF4KW)
[Download Android Studio & App Tools - Android Developers](https://developer.android.com/studio?gclid=Cj0KCQiAjJOQBhCkARIsAEKMtO3zEhdK4_I0CEZic3UH4dl-9gVXuHFR9dCl3TOHKjmv3xWLU3UxfhYaApfAEALw_wcB&gclsrc=aw.ds)

安裝完 Android SDK 和 Android Studio 後，新增環境變數 ANDROID_HOME，並將變數值設定為 SDK 存放路徑
![Pasted image 20230719000127](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/Pasted%20image%2020230719000127.png?token=AGFDTP7IAXD5TBV34HJ5BX3EXF4L2)

再透過 flutter doctor --android -licenses 指令同意一些授權
![Pasted image 20230719000152](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/Pasted%20image%2020230719000152.png?token=AGFDTP3AJOTO5646YYYGMNDEXF4NA)

再到 Android Studio>Plugins 安裝 Flutter ，同時還會安裝 Dart
![ImagesPasted image 20230719000f217](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/ImagesPasted%20image%2020230719000f217.png?token=AGFDTP6EWX7ZMQSC2W22ZG3EXF4WA)

<br>

## Visual Studio Code 設定
啟動 VS Code ，點選擴充功能並安裝 `Flutter` 和 `Android iOS Emulator` ， Dart 會和 Flutter 同時被安裝
![Pasted image 2023071900030d4](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/Pasted%20image%202023071900030d4.png?token=AGFDTP7NMIQC5MMESE6OR5TEXF4O4)