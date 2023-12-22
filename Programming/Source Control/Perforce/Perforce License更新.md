---
date: 2023-12-21
tags:
  - SourceControl
  - Perforce
---
---
打開 P4admin 登入管理員帳號，在 Home>UserLicenses 頁面可以看到 Licenses 到期日

//圖

購買 License 後會得的一個文件如下

//圖

將其改名為 `license` （沒有副檔名）

//圖

再將其放入 Perforce Server 的 database 資料夾

//圖

接著，以管理員權限開啟 CMD 輸入：
```
P4 admin restart
```
> 若 CMD 指令無效，理論上重開機後 Helix Server 也會重啟

重啟成功後回到 P4admin 就會看到 License 更新了
