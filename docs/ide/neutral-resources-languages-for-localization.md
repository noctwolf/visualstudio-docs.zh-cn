---
title: 用于本地化的非特定资源语言
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- localization [Visual Studio], resources
- NeutralResourcesLanguageAttribute class
- globalization [Visual Studio], resources
- resources [Visual Studio], fallback system
- culture, locating resources
- neutral resources
ms.assetid: ef064995-3b84-4698-a708-9689b7723533
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 34013c0b896f47e919a105680d18812aaba60dd0
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49906983"
---
# <a name="neutral-resources-languages-for-localization"></a>用于本地化的非特定资源语言

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

- <xref:System.Resources.ResourceManager>
- [基于 .NET Framework 的国际应用程序简介](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md)
- [用于本地化的资源的分层组织](../ide/hierarchical-organization-of-resources-for-localization.md)
- [本地化应用程序](../ide/localizing-applications.md)
- [对应用程序进行全球化和本地化](../ide/globalizing-and-localizing-applications.md)