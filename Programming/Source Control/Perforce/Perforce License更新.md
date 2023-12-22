---
date: 2023-12-21
tags:
  - SourceControl
  - Perforce
---
---
打開 P4admin 登入管理員帳號，在 Home>UserLicenses 頁面可以看到 Licenses 到期日

![2023-12-22 145136](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-12-22%20145136.png)

購買 License 後會得的一個文件如下

![2023-12-22 145235](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-12-22%20145235.png)

將其改名為 `license` （沒有副檔名）

![2023-12-22 145307](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-12-22%20145307.png)

再將其放入 Perforce Server 的 database 資料夾

![2023-12-22 145324](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/2023-12-22%20145324.png)

接著，以管理員權限開啟 CMD 輸入：
```
P4 admin restart
```
> 若 CMD 指令無效，理論上重開機後 Helix Server 也會重啟

重啟成功後回到 P4admin 就會看到 License 更新了
