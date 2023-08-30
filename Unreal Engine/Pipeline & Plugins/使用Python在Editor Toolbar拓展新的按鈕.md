---
date : 2023-08-29
tags : UE5 Editor Python Slate
---
Status::🌱
---

```
import unreal

# Get editor ToolBar ref
menus = unreal.ToolMenus.get()
menu_name = "LevelEditor.LevelEditorToolBar.User"
menu = menus.find_menu(menu_name)
entry.set_icon("EditorStyle","Menu.Icon")

command = unreal.ToolMenuStringCommandType.PYTHON
entry.set_string_command(command, "", 'print("Hello")')
menu.add_menu_entry("", entry)
        
menus.refresh_all_widgets()
```


> Python 腳本中無法使用自定義的 Icon，只能使用引擎內建的 Icon

可參考Engine source code `SlateEditorStyle.cpp` 
或這個網站
https://github.com/EpicKiwi/unreal-engine-editor-icons

若還是想使用自定義的 Icon，還是得用 C++註冊自己的圖
![[在Editor Toolbar使用自定義的Icon]]