---
date : 2023-08-29
tags : UE5 Editor Plugin Slate
---
Status::🌱
---
>在 Unreal Editor 中可使用 **FSlateStyleSet** 來新增自定義的 icons 或 thumbnails，以下以在新創建的 plugin 中的 Toolbar 按鈕上使用自定義的 icon 作為範例

創建一個新的 plugin 後，在 Build.cs 中新增 `Projects` module
```
//Build.cs
PrivateDependencyModuleNames.AddRange(
	new string[]
	{
	"CoreUObject",
	"Engine",
	"Slate",
	"SlateCore",
	"Sockets" ,
	"Projects" // <-add this Module for using FSlateStyleSet
	}
```