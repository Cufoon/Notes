---
title: "添加Git Bash Here到右键菜单"
date: 2019-04-20T22:19:56+08:00
draft: false
tags: ["Windows"]
---
1. 打开注册表，定位到HKEY_CLASSES_ROOT\Directory\Background\shell，Background下没有shell目录，则新建
2. 在shell上右键→新建项,其名称为“Git Bash Here”，此为右键菜单显示名称（也可以将该项命名为Git，然后在该项的默认值中填上“Git Bash Here”,也能在右键菜单显示出来“Git Bash Here”）
3. 在2中新建的项上右键→新建→字符串，命名为Icon，双击编辑，其值为“Git安装目录\mingw64\share\git\git-for-windows.ico”。此为菜单项的图标
4. 在2中新建的项上右键→新建→项，命名为command，其值为”Git安装目录\git-bash.exe” 