---
title: "VS Shell 部署 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: eb5446c8c3090624f327c234a1b518dc1928b6c9
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
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