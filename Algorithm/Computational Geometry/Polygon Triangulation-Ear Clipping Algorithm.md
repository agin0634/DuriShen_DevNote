---
date: 2024-08-17
tags:
  - Algorithm
  - Geometry
  - Triangulation
---
---
> Ear Clipping 算法用於將簡單多邊形拆解成一系列三角形：
> 
> ![screenshot 2024-08-17 at 1.07.42 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-17%20at%201.07.42%20PM.jpg)

<br>

## 定義
簡單多邊形(Simple Polygon)的定義如下：
1. 由n個頂點組成，n-2個三角形，n-3條對角線
2. 多邊形內沒有破洞
3. 每個頂點只有兩條線相連，且線不相交

![screenshot 2024-08-17 at 1.09.56 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-17%20at%201.09.56%20PM.jpg)

耳(ear)是凸點及兩個相鄰點組成的三角形
嘴(mouth)是凹點及兩個相鄰點組成的三角形

![screenshot 2024-08-17 at 1.17.49 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-17%20at%201.17.49%20PM.jpg)
<br>
## 演算過程
1. 建立多邊形點的資料結構成 circular linked list
2. 窮舉所有點，判斷是否為耳
3. 若為耳，再判斷是否有組成耳3點以外的點在三角形內
4. 若無，則切耳，回到步驟2
5. 直到剩下最後3個點，此為最後的三角形

![screenshot 2024-08-17 at 1.55.11 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/screenshot%202024-08-17%20at%201.55.11%20PM.jpg)

## Ref
[Triangulation by Ear Clipping (geometrictools.com)](https://www.geometrictools.com/Documentation/TriangulationByEarClipping.pdf)
[triangulation - 演算法筆記 (ntnu.edu.tw)](https://web.ntnu.edu.tw/~algo/Triangulation.html)
[Ear Clipping算法简介-CSDN博客](https://blog.csdn.net/AndrewFan/article/details/103376907)