---
title: 如何： 禁止显示生成的代码的代码分析警告 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 81bb371a3e16236e22ab3a1fd4ac5ab431f61512
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471447"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>如何：禁止显示所生成代码的代码分析警告
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 生成代码的禁止显示代码分析警告](https://docs.microsoft.com/visualstudio/code-quality/how-to-suppress-code-analysis-warnings-for-generated-code)。  
  
托管的代码编译器通常会生成添加到项目，以便加快代码的开发的代码。 此外，开发人员通常使用第三方工具来帮助快速开发应用程序。 这些工具还生成添加到项目的代码。  
  
 您可能想要看到的代码分析在生成的代码中发现的规则冲突。 但是，可能不想要查看它们是否不能查看和维护包含冲突的代码。  
  
 **禁止显示生成代码的结果**项目的代码分析属性页上的复选框使您可选择是否想要查看从第三方工具生成的代码的代码分析警告。  
  
> [!NOTE]
>  此选项不会取消代码分析错误和生成的代码时的错误和警告出现在窗体和模板。 可以查看和维护窗体或模板的源代码。  
  
### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>若要禁止显示项目中生成代码的警告  
  
1.  右键单击解决方案资源管理器中的项目，然后单击**属性**。  
  
2.  单击**代码分析**。  
  
3.  选择**禁止显示生成代码的结果**复选框。



