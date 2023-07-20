---
date : 2023-07-21 01:03
tags : Hardware VR Vive
---

## 設置SteamVR

前往你的Steam安裝路徑並找到`null driver`資料夾

>\steamapps\common\SteamVR\drivers\null\resources\settings\

修改`default.vrsettings
```
"enable" : true,
```

<br>

接著，前往

>\steamapps\common\SteamVR\resources\settings

修改`default.vrsettings`
```
"requireHmd": false,
"forcedDriver": "null",
"activateMultipleDrivers": true,
```

<br>

## 開啟SteamVR並連結Tracker

開啟SteanVR後會看到此畫面
![Pasted image 20230721010737](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/ImagesPasted%20image%2020230721010737.png?token=AGFDTP2M7WUZEJAR5S6R2ATEXF3MG)