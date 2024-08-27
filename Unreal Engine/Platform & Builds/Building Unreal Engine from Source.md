---
date: 2024-08-24
tags:
  - UE4
  - UE5
  - Build
Version: UE5.3
---
---
## 加入 Epic Games Organization
連結自己的 Epic Games 和 Github 帳號

![screenshot 2024-08-24 at 4.34.33 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-24%20at%204.34.33%20PM.jpg)

連結成功後，打開 Github 就會被邀請到 Epic Games 的 Organization 

![screenshot 2024-08-24 at 4.41.32 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-24%20at%204.41.32%20PM.jpg)
<br>
## 下載 Unreal Engine source code
找到 Unreal Engine 的 repository，選擇想要下載的版本分支並下載

![screenshot 2024-08-24 at 4.46.10 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-24%20at%204.46.10%20PM.jpg)
<br>
## 安裝 Visual Studio 及相關套件
先確認下載的 Unreal 版本及其支援的 VS 版本

並安裝以下套件：
- .NET 桌面開發
- C++ 桌面開發
- Windows 應用程式開發
- C++ 遊戲開發
- Windows SDK

![screenshot 2024-08-27 at 6.15.55 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-27%20at%206.15.55%20PM.jpg)
<br>

## 編譯引擎
1. 解壓縮檔案，建議不要放在超過50個字的檔案路徑
2. 執行 Setup.bat，此步驟會下載依賴的檔案，會花一點時間
3. 執行 GenerateProjectFiles.bat 生成 sln 專案檔
4. 開啟 UE5.sln，方案組態設定為 `Development Editor`，平台為 `Win64`
   
   ![screenshot 2024-08-27 at 6.16.57 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-27%20at%206.16.57%20PM.jpg)
5. 設定啟動專案並開始建置
   
   ![screenshot 2024-08-27 at 6.17.40 PM | 300](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-27%20at%206.17.40%20PM.jpg)
6. 建置成功後到 Engine>Binaries>Win64，找到 UnrealEditor.exe，點擊後即可啟動編輯器
   
   ![screenshot 2024-08-27 at 6.18.55 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-27%20at%206.18.55%20PM.jpg)
