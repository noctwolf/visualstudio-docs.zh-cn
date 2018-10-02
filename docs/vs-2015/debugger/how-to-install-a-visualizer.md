---
title: 如何： 安装可视化工具 |Microsoft Docs
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
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5152c47635f8ca2f2bb0a6a32c7767682006860a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484300"
---
# <a name="how-to-install-a-visualizer"></a>如何：安装可视化工具
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 安装可视化工具](https://docs.microsoft.com/visualstudio/debugger/how-to-install-a-visualizer)。  
  
创建了可视化工具后，您还必须安装该可视化工具，这样您才可在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中使用它。 安装可视化工具是个简单的过程。  
  
> [!NOTE]
>  在中**Store**应用，仅在标准文本支持 HTML、 XML 和 JSON 可视化工具。 不支持自定义（用户创建的）可视化工具。  
  
### <a name="to-install-a-visualizer"></a>安装可视化工具  
  
1.  查找包含已创建的可视化工具的 DLL。  
  
2.  将 DLL 复制到下列位置之一：  
  
    -   *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3.  若要使用托管可视化工具进行远程调试，请将 DLL 复制到远程计算机上的同一路径。  
  
4.  重新启动调试会话。  
  
## <a name="see-also"></a>请参阅  
 [创建自定义可视化工具](../debugger/create-custom-visualizers-of-data.md)   
 [如何：编写可视化工具](../debugger/how-to-write-a-visualizer.md)



