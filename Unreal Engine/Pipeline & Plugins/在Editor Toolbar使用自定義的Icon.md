---
date: 2023-08-29
tags:
  - UE5
  - Editor
  - Plugin
  - Slate
  - Cpp
---
---
>在 Unreal Editor 中可使用 **FSlateStyleSet** 來新增自定義的 icons 或 thumbnails，以下以在新創建的 plugin 中的 Toolbar 按鈕上使用自定義的 icon 作為範例

<br>

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
)
```

創建 MyStyle.h 和 MyStyle.cpp
```
//MyStyle.h
#pragma once

#include "CoreMinimal.h"

//Additional Includes
#include "Styling/SlateStyle.h"
#include "Styling/SlateStyleRegistry.h"

class FMyStyle
{
public:
	static void Initialize();

	static void Shutdown();

private:
	static TSharedRef< class FSlateStyleSet > Create();

private:
	static TSharedPtr< class FSlateStyleSet > StyleInstance;
};
```

```
//MyStyle.cpp
#include "Style.h"

//Additional Includes
#include "Interfaces/IPluginManager.h"
#include "Styling/SlateStyleMacros.h"

#define RootToContentDir Style->RootToContentDir

TSharedPtr<FSlateStyleSet> FMyStyle::StyleInstance = nullptr;

//Common sizes for icons and thumbnails
const FVector2D Icon64x64(64.f, 64.f);
const FVector2D Icon40x40(40.0f, 40.0f);
const FVector2D Icon20x20(20.0f, 20.0f);
const FVector2D Icon16x16(16.0f, 16.0f);
const FVector2D Icon12x12(12.0f, 12.0f);

void FMyStyle::Initialize()
{
	if (!StyleInstance.IsValid())
	{
		StyleInstance = Create();
		FSlateStyleRegistry::RegisterSlateStyle(*StyleInstance);
	}
}

void FMyStyle::Shutdown()
{
	FSlateStyleRegistry::UnRegisterSlateStyle(*StyleInstance);
	StyleInstance.Reset();
}

TSharedRef<class FSlateStyleSet> FMyStyle::Create()
{
	//Create a new style set
	TSharedRef<FSlateStyleSet> Style = MakeShareable(new FSlateStyleSet("MyStyle"));

	//Set the content Root directory of our plugin in order to access the images
	Style->SetContentRoot(IPluginManager::Get().FindPlugin("MyPlugin")->GetBaseDir() / TEXT("Resources"));

	//Set the Images of the properties to be equal of new images
	//Include `SlateStyleMacros.h` to use this marco
	Style->Set("MyStyle.ToolbarButton", new IMAGE_BRUSH(TEXT("Icon128"), Icon20x20));
	Style->Set("MyStyle.ToolbarButtonSmall", new IMAGE_BRUSH(TEXT("Icon128"), Icon16x16));

	return Style;
}
```
>這邊設定的 Root 路徑是 Plugin 下的 Resources，所以將圖片放在此資料夾

<br>

接著到 Plugin.cpp
```
//MyPlugin.cpp
#include "MyXRPlugin.h"

//Incldue MyStyle header
#include "MyStyle.h"

#define LOCTEXT_NAMESPACE "FMyPluginModule"

void FMyPluginModule::StartupModule()
{
	FMyStyle::Initialize();
}

void FMyPluginModule::ShutdownModule()
{
	FMyStyle::Shutdown();
}

#undef LOCTEXT_NAMESPACE
	
IMPLEMENT_MODULE(FMyPluginModule, MyPluginModule)
```

Compile 後，重啟編輯器
![20230830_87815165](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/Archives/Images/20230830_87815165.png)