---
date: 2023-08-30
tags:
  - UE5
  - Python
  - Slate
  - EditorScripting
Version: UE5.3
---
---
>使用 Python 擴展編輯器雖然沒使用 C++ 來的靈活，但寫起來更簡單且快速 

<br>

創建一個 `init_unreal.py`

```python
# init_unreal.py
import unreal

# Get editor toolbar menu
menus = unreal.ToolMenus.get()
menu_name = "LevelEditor.LevelEditorToolBar.User"
menu = menus.find_menu(menu_name)

# register menu entry
entry = unreal.ToolMenuEntry(type=unreal.MultiBlockType.TOOL_BAR_BUTTON)
entry.set_label("MyButton")
entry.set_tool_tip("My Button Tooltip")
entry.set_icon("EditorStyle","Menu.Icon")

# register command
command = unreal.ToolMenuStringCommandType.PYTHON
entry.set_string_command(command, "", 'print("Hello")')
menu.add_menu_entry("", entry)
        
menus.refresh_all_widgets()
```


點擊按鈕後打印出 Hello

![2023-08-30 2156445455](https://raw.githubusercontent.com/agin0634/DuriShen_DevNote/main/_Archives/Images/2023-08-30%202156445455.png)

> Python 腳本中無法使用自定義的 Icon，只能使用引擎內建的 Icon

可參考Engine source code `SlateEditorStyle.cpp` 
或這個網站
https://github.com/EpicKiwi/unreal-engine-editor-icons

<br>

若還是想使用自定義的 Icon，還是得用 C++註冊自己的圖
![[在Editor Toolbar使用自定義的Icon]]