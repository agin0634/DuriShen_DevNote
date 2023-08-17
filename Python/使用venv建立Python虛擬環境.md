---
date : 2023-08-17
tags : Python VirtualEnv
---
Status::🌱
---
## 建立虛擬環境
**Windows:**
```
py -m venv venvname
```
**Mac:**
```
python -m venv venvname
```

<br>

## 進入虛擬環境

**Windows:**
```
.\venvname\Scripts\activate.bat
```

若使用 PowerShell, 而不是使用**命令提示字元**, 則執行
```
.\venvname\Scripts\activate.ps1
```
**Mac:**
```
source ./venvname/bin/activate
```

<br>

## 離開虛擬環境
**Windows/Mac:**
```
deactivate
```

<br>

## 刪除虛擬環境
離開虛擬環境後，再將虛擬環境的資料夾刪除即可

<br>

## Ref
[12. 虛擬環境與套件 — Python 3.11.4 說明文件](https://docs.python.org/zh-tw/3/tutorial/venv.html)
