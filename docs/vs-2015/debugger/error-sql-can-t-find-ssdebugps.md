---
title: 错误： SQL 可以&#39;t 不到 Ssdebugps |Microsoft Docs
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
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- FSharp
- VB
- CSharp
- C++
- SQL
ms.assetid: 596425c8-14c7-4c05-8823-e1c52f420f5e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1782412ded2c4edff0da29b13160107664170d20
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482351"
---
# <a name="error-sql-can39t-find-ssdebugps"></a>错误： SQL 可以&#39;t 不到 Ssdebugps
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[错误： SQL 可以&#39;t 查找 SSDEBUGPS](https://docs.microsoft.com/visualstudio/debugger/error-sql-can-t-find-ssdebugps)。  
  
SSDEBUGPS.dll 为 SQL Server Debugging Host 组件。  
  
 此错误在尝试开始调试时发生，指示指定的文件在 [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] 计算机上不存在。 可能的原因是从未运行远程调试安装，或是由于某种原因删除了此文件。  
  
 若要解决此错误的两种方式： 通过重新运行远程调试安装，并通过复制文件拖放到[!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)]机。  
  
 若要重新运行远程调试安装，请按照的说明[远程调试](../debugger/remote-debugging.md)。  
  
 如果可以找到 ssdebugps.dll 的某个副本，可以将其拖到复制[!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)]机。 如果存在，该文件会位于目录 \Program Files\ Common Files\Microsoft Shared\SQL Debugging 中。 你可能会发现它在另一台[!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)]的计算机上的计算机或[!INCLUDE[vsprvslong](../includes/vsprvslong-md.md)]安装。  
  
### <a name="to-copy-ssdebugpsdll-onto-the-sql-server-2005-machine"></a>将 SSDEBUGPS.dll 复制到 SQL Server 2005 计算机上  
  
1.  将文件复制到具有相同名称和路径的目录上[!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)]机。  
  
2.  通过打开注册**命令提示符下**，并运行以下命令：  
  
    ```  
    regsrv32 ssdebugps.dll  
    ```



