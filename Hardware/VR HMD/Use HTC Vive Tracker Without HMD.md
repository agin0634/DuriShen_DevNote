---
date : 2023-07-21
tags : Hardware VR Vive
---
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
![ImagesPasted image 202307210145s077](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/ImagesPasted%20image%20202307210145s077.png)