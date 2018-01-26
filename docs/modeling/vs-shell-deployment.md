---
title: "VS Shell 部署 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 26b5075c36b152ecc44d65428521e191e6053609
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="vs-shell-deployment"></a>VS Shell 部署

独立的 shell，可以确定哪些 Visual Studio 需要与你的域特定语言和该解决方案的显示方式进行交互的功能。 有关 Visual Studio 独立 shell 的详细信息，请参阅[自定义独立 Shell](../extensibility/customizing-the-isolated-shell.md)。

## <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>若要将 Visual Studio Shell 设置为部署目标
  
1.  在**DslPackage**项目中，打开**source.extension.tt**。  
  
2.  下`<SupportedProducts>`插入：  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     替换*MyIsolatedShell*与独立的 shell 包的名称。