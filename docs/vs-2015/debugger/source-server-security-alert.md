---
title: 源服务器安全警报 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.sourceserver.enablewarning
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b971a05f9cd8873a1dbac3cafe6865ffce238868
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472235"
---
# <a name="source-server-security-alert"></a>源服务器安全警报
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[源服务器安全警报](https://docs.microsoft.com/visualstudio/debugger/source-server-security-alert)。  
  
使用源服务器时，只能使用来自已知和受信任位置的符号文件。  
  
 此警告会在你启用源服务器支持时出现。 源服务器命令嵌套在调试符号文件（PDB 文件）中。 请确保你知道自己的 PDB 文件来自何处。  
  
> [!IMPORTANT]
>  使用源服务器时必须考虑以下潜在的安全威胁：因为任何命令都可以嵌入到应用程序的 PDB 文件中，所以请确保只将要执行的命令放到 srcsrv.ini 文件中。 任何尝试执行不在 srcsvr.ini 文件中的命令都将导致出现一个确认对话框。 有关详细信息，请参阅[安全警告： 调试器必须执行不受信任的命令](../debugger/security-warning-debugger-must-execute-untrusted-command.md)。命令参数进行任何验证，所以请小心使用受信任的命令。 例如，如果你信任 cmd.exe，恶意用户则可能会指定使该命令变得危险的参数。  
  
## <a name="see-also"></a>请参阅  
 [指定符号 (.pdb) 和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [调试器安全](../debugger/debugger-security.md)   
 [源服务器](http://msdn.microsoft.com/library/windows/desktop/ms680641.aspx)



