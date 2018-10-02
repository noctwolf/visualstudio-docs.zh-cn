---
title: SDI 服务器应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- SDI server applications
- SDI server applications, debugging
ms.assetid: 09713718-1376-4753-b119-26f36639693e
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c6ee3ee3a1273c02dd094f89c099230024eabfc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483560"
---
# <a name="sdi-server-applications"></a>SDI 服务器应用程序
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[SDI 服务器应用程序](https://docs.microsoft.com/visualstudio/debugger/sdi-server-applications)。  
  
如果正在调试 SDI 服务器应用程序，则必须指定`/Embedding`或`/Automation`中**命令行参数**中的属性*项目*C/c + +，C# 中，属性页对话框或Visual Basic 项目。  
  
 使用这些命令行自变量，调试器可以像从容器中启动服务器应用程序一样启动它。 从程序管理器或文件管理器启动容器将导致容器使用在调试器中启动的服务器实例。  
  
## <a name="finding-the-command-line-arguments-property"></a>查找“命令行自变量”属性  
 访问*项目*属性页对话框中，右键单击解决方案资源管理器中的项目，然后从快捷菜单中选择属性。 若要找到“命令行自变量”属性，请展开“配置属性”类别并单击“调试”页。  
  
## <a name="see-also"></a>请参阅  
 [调试 COM 和 ActiveX](../debugger/com-and-activex-debugging.md)   
 [如何：调试 COM 服务器](../debugger/how-to-debug-com-servers.md)



