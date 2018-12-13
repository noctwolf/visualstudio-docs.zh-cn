---
title: 用于本地化的非特定资源语言 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 45fadacc75b2772ba32d7cb0d796c972076b81ef
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49256684"
---
# <a name="neutral-resources-languages-for-localization"></a>用于本地化的非特定资源语言
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:System.Resources.NeutralResourcesLanguageAttribute> 类指定包含在主程序集中的资源的区域性。 此属性作为增强性能使用，以便 <xref:System.Resources.ResourceManager> 对象不会搜索包含在主程序集中的资源。  
  
 以下代码演示如何设置非特定资源语言。 可以将代码放置在生成脚本或 AssemblyInfo.vb 或 AssemblyInfo.cs 文件中。  
  
```vb  
' Set neutral resources language for assembly.  
<Assembly: NeutralResourcesLanguageAttribute("en")>  
  
```  
  
```csharp  
// Set neutral resources language for assembly.  
[assembly: NeutralResourcesLanguageAttribute("en")]  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Resources.ResourceManager>   
 [基于 .NET Framework 的国际应用程序简介](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)   
 [用于本地化的资源的分层组织](../ide/hierarchical-organization-of-resources-for-localization.md)   
 [本地化应用程序](../ide/localizing-applications.md)   
 [对应用程序进行全球化和本地化](../ide/globalizing-and-localizing-applications.md)

