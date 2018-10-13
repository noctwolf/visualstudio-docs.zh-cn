---
title: 通过使用修改独立的 Shell。Pkgundef 文件 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, isolated mode%2C .pkgundef file
ms.assetid: 9cee2a20-f8ac-4d9d-aef9-068fcd9f27a4
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5663c3e7f8dfb3460e163c851751bde95fb630d2
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49256420"
---
# <a name="modifying-the-isolated-shell-by-using-the-pkgundef-file"></a>通过使用修改独立的 Shell。Pkgundef 文件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

你可以修改.pkgundef 文件以排除指定的注册表条目从独立的 shell 应用程序。 通常情况下，第一次的计算机，启动的应用程序的 Visual Studio shell 的现有 Visual Studio 注册表项复制到应用程序的根注册表项。 这包括对当前安装的 Vspackage 的任何引用。  
  
 若要从独立的 shell 应用程序中排除特定的注册表项，将添加到应用程序.pkgundef 文件包键，再按该条目。 项和条目都是一样的.pkgdef 文件;也就是说，作为 [$RootKey$] 或 [$RootKey$\\*子项*] 和"*条目*"=*值*，其中*子项*是子项，以便影响*条目*是要删除的项并*值*可以是`""`或`dword:00000000`。  
  
 若要从注册表项中排除多个条目，只是列出密钥一次后, 跟每个要排除的项的行。  
  
 若要从独立的 shell 应用程序排除整个注册表项，请将该密钥添加到应用程序.pkgundef 文件但未指定该密钥的任何注册表项。  
  
 可以将注释添加到.pkgundef 文件。 单行注释必须具有两个斜杠作为前两个字符。  
  
 例如，若要删除**连接到数据库**并**连接到提供 r**上的命令**工具**菜单中，可以取消注释行：  
  
```  
[$RootKey$\Packages\{8D8529D3-625D-4496-8354-3DAD630ECC1B}]  
```  
  
 并添加行：  
  
```  
[$RootKey$\Packages\{198E76C1-34C0-424D-9957-B3EBD80265FB}]  
```  
  
 为应用程序的.pkgundef 文件。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 功能的包 Guid](../extensibility/package-guids-of-visual-studio-features.md)   
 [自定义独立 Shell](../extensibility/customizing-the-isolated-shell.md)

