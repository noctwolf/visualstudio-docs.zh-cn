---
title: 错误： Windows 文件共享已配置...|Microsoft Docs
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
- vs.debug.error.remote_credentials_prohibited
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: c45a1b74-61ec-4c64-9e2c-13051a4f50a5
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9fc4d3fb02b1c7c9d5003f82fbe42be73c93d6eb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476763"
---
# <a name="error-windows-file-sharing-has-been-configured"></a>错误：已配置 Windows 文件共享...
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[错误： 已配置 Windows 文件共享...](https://docs.microsoft.com/visualstudio/debugger/error-windows-file-sharing-has-been-configured-dot-dot-dot).  
  
已配置 Windows 文件共享，因此您将使用另一不同的用户名连接到远程计算机。 这与远程调试不兼容  
  
 当前文件共享配置设置为使用另一用户名连接到远程计算机。 在这种情况下不能进行远程调试。  
  
 若要更正此错误，请使用其他帐户名登录到计算机上，或是更改文件共享以使用要用来进行调试的帐户名。  
  
 如果要使用此用户名连接到远程计算机，则必须首先从远程计算机断开连接。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
1.  使用其他帐户名登录到本地计算机（要从其进行调试的计算机）上。  
  
     - 或 -  
  
     . 中断与远程计算机的连接，然后重新配置文件共享，以便使用您的帐户名称连接至其他计算机：  
  
    1.  上**启动**菜单，依次指向**附件**，然后单击**命令提示符下**。  
  
    2.  在 Windows 命令提示处，键入：  
  
         `net use /delete computer_name`  
  
    3.  使用 Windows 帮助中介绍的任一方法更改文件共享设置。



