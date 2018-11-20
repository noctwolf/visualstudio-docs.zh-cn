---
title: 如何： 调试 ActiveX 控件 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.controls.debug
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- testing [Visual Studio], test containers
- ActiveX control container debugging [Visual Studio]
- debugging ActiveX controls
- data-bound controls, ActiveX
- test container
- containers, specifying for debug sessions
- ActiveX controls, debugging
- testing [Visual Studio], ActiveX controls
ms.assetid: bbc02cf7-a7e6-44fe-99af-87a43e1d7251
caps.latest.revision: 19
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f1e43d94807fa28f86193fc7818b77887d797772
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51745160"
---
# <a name="how-to-debug-an-activex-control"></a>如何：调试 ActiveX 控件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

请注意]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在“工具”菜单上选择“导入和导出设置”。 有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
 若要调试 ActiveX 控件，必须指定一个容器（可执行文件）用于运行控件。  
  
### <a name="to-specify-a-container-for-the-debug-session"></a>为调试会话指定容器  
  
1.  在“解决方案资源管理器”中，选择项目。  
  
2.  从**视图**菜单中，选择**属性页**。  
  
3.  在中**项目属性页**对话框中，打开**配置属性**文件夹，然后选择**调试**。  
  
4.  下**调试**类别中，找到**命令**属性。  
  
5.  指定容器的路径名。 例如，C:\Program Files\Internet Explorer\IEXPLORE.EXE。  
  
6.  如果为容器指定 Internet Explorer，并且正在使用 Active Desktop，请键入`/new`中**命令参数**框。  
  
7.  单击 **“确定”**。  
  
     如果未指定的容器中**项目属性页**对话框中，您可以指定容器时开始调试。 选择执行命令来启动调试，当[调试会话对话框的可执行文件](../debugger/executable-for-debugging-session-dialog-box.md)出现。 在对话框中指定容器的路径名。  
  
## <a name="see-also"></a>请参阅  
 [ActiveX 控件](http://msdn.microsoft.com/library/52aaec4d-3889-402e-b57d-758078f8ac57)   
 [使用测试容器测试属性和事件](http://msdn.microsoft.com/library/626867cf-fe53-4c30-8973-55bb93ef3917)   
 [调试 COM 和 ActiveX](../debugger/com-and-activex-debugging.md)   
 [在 Visual Studio 中进行调试](../debugger/debugging-in-visual-studio.md)



