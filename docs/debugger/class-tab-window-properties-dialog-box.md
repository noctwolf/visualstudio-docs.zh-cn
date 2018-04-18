---
title: 类窗口属性对话框中选项卡 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
helpviewer_keywords:
- Window Properties dialog box, Class Tab
ms.assetid: eaec9f07-d580-436d-934d-76c4e59439aa
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 573eb3f9cbcaedddc67524e81b2508df2112de04
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="class-tab-window-properties-dialog-box"></a>“窗口属性”对话框 ->“类”选项卡
使用**类**选项卡来显示对所选的窗口类信息。 若要显示[窗口属性对话框](../debugger/window-properties-dialog-box.md)，焦点移到[Windows 视图](../debugger/windows-view.md)窗口。 在树中，选择任何窗口节点，然后选择**属性**从**视图**菜单。  
  
 以下设置子网上有**类**选项卡：  
  
|条目|描述|  
|-----------|-----------------|  
|**类名**|此窗口类的名称 （或序号）。|  
|**类样式**|类样式代码的组合。|  
|**类字节**|与此窗口类关联的应用程序特定数据。|  
|**类 Atom**|返回的类的 atom **RegisterClass**调用。|  
|**实例句柄**|注册此类的模块的实例句柄。 实例句柄不是唯一的。|  
|**窗口字节**|与此类的每个窗口关联的额外字节数。 这些字节的含义取决于应用程序。 展开该列表框，以查看 DWORD 格式中的字节值。|  
|**窗口进程**|当前地址**WndProc**适用于 windows 的此类的函数。 这不同于**窗口进程**上**常规**选项卡上，如果对窗口子类化。|  
|**菜单名称**|与此类 （如果没有任何菜单"无"） 的窗口相关联的主菜单的名称。|  
|**图标的句柄**|图标与此类 （如果有任何图标"无"） 的窗口的句柄。|  
|**光标句柄**|与此类 （如果没有任何光标"无"） 的窗口相关联的光标句柄。|  
|**背景画笔**|与此类，或其中一个的预定义 COLOR_ * 颜色绘制窗口背景 （如果存在无画笔"无"） 的 windows 相关联的背景画笔句柄。|