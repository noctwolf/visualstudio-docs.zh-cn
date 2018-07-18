---
title: 错误： 远程计算机未显示在远程连接对话框 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c52a2ebd99b052171220fd8a06f1ae7ff5dc258e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31471328"
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>错误：远程计算机未显示在“远程连接”对话框中
如果远程计算机未显示在“远程连接”对话框中，请检查以下常见原因。  
  
 如果你使用托管的兼容模式，请检查的 Visual Studio 2010 文档： [远程调试疑难解答 - Visual Studio 2010](https://msdn.microsoft.com/en-us/library/2ys11ead\(v=vs.100\).aspx) 。  
  
### <a name="common-causes-for-this-error"></a>导致此错误的常见原因  
  
-   远程计算机正在位于不同子网中的计算机上运行。 若要解决此问题，在限定符对话框中手动键入计算机名称或 IP 地址  
  
-   远程调试器未在远程计算机上运行。 若要解决此问题，启动远程调试器。  
  
-   防火墙正在阻止 Visual Studio 和远程计算机之间的通信。 若要解决此问题，请将防火墙配置为允许 Visual Studio 和远程调试器 (msvsmon) 进行通信。  
  
-   防病毒软件正在阻止 Visual Studio 和远程计算机之间的通信。 若要解决此问题，请将防病毒软件配置为允许 Visual Studio 和远程调试器 (msvsmon) 进行通信。  
  
## <a name="see-also"></a>请参阅  
 [远程调试](../debugger/remote-debugging.md)