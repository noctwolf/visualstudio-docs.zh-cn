---
title: 源服务器安全警报 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.sourceserver.enablewarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 8451c281-6914-469c-b80c-6271cc3f3d17
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f732586581c1e7c4634d4a3d7e9d904cd5ea46ca
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54991471"
---
# <a name="source-server-security-alert"></a>源服务器安全警报
使用源服务器时，只能使用来自已知和受信任位置的符号文件。  
  
 此警告会在你启用源服务器支持时出现。 源服务器命令嵌套在调试符号文件（\*.pdb 文件）中。 请确保你知道自己的 PDB 文件来自何处。  
  
> [!IMPORTANT]
>  使用源服务器时，必须考虑以下潜在安全威胁：任意命令都可嵌入应用程序的 .pdb 文件中，因此请确保在 srcsrv.ini 文件中仅放入要执行的命令。 任何尝试执行不在 srcsvr.ini 文件中的命令都将导致出现一个确认对话框。 有关详细信息，请参阅[安全警告：调试器必须执行不受信任的命令](../debugger/security-warning-debugger-must-execute-untrusted-command.md)。 未对命令参数执行任何验证，因此请慎用受信任的命令。 例如，如果你信任 cmd.exe，恶意用户则可能会指定使该命令变得危险的参数。  
  
## <a name="see-also"></a>请参阅  
 [指定符号 (.pdb) 文件和源文件](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [调试器安全](../debugger/debugger-security.md)   
 [源服务器](/windows/desktop/Debug/source-server-and-source-indexing)
