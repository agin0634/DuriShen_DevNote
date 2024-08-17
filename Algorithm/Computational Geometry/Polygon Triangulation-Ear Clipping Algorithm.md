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
> ![screenshot 2024-08-17 at 1.07.42 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-08-17%20at%201.07.42%20PM.jpg)

<br>

## 定義
簡單多邊形(Simple Polygon)的定義如下：
1. 由n個頂點組成，n-2個三角形，n-3條對角線
2. 多邊形內沒有破洞
3. 每個頂點只有兩條線相連，且線不相交

![screenshot 2024-08-17 at 1.09.56 PM](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/screenshot%202024-08-17%20at%201.09.56%20PM.jpg)

## Ref
[Triangulation by Ear Clipping (geometrictools.com)](https://www.geometrictools.com/Documentation/TriangulationByEarClipping.pdf)
[triangulation - 演算法筆記 (ntnu.edu.tw)](https://web.ntnu.edu.tw/~algo/Triangulation.html)