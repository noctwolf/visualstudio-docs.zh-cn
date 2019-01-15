---
title: SDI 服务器应用程序 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- SDI server applications
- SDI server applications, debugging
ms.assetid: 09713718-1376-4753-b119-26f36639693e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ec4178fb23d84812d7258bac8384264bed9d4690
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53885046"
---
# <a name="sdi-server-applications"></a>SDI 服务器应用程序
如果调试的是 SDI 服务器应用程序，对于 C/C++、C# 或 Visual Basic 项目，必须在“项目属性页”对话框中的“命令行参数”属性中指定 `/Embedding` 或 `/Automation`。  
  
 使用这些命令行自变量，调试器可以像从容器中启动服务器应用程序一样启动它。 从程序管理器或文件管理器启动容器将导致容器使用在调试器中启动的服务器实例。  
  
## <a name="finding-the-command-line-arguments-property"></a>查找“命令行自变量”属性  
 若要访问“项目属性页”对话框，请在解决方案资源管理器中右键单击项目，然后从快捷菜单中选择“属性”。 若要找到“命令行自变量”属性，请展开“配置属性”类别并单击“调试”页。  
  
## <a name="see-also"></a>请参阅  
 [调试 COM 和 ActiveX](../debugger/com-and-activex-debugging.md)   
 [如何：调试 COM 服务器](../debugger/how-to-debug-com-servers.md)