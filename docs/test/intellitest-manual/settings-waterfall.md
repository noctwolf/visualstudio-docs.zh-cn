---
title: "设置瀑布图 | Microsoft IntelliTest 开发人员测试工具 | Microsoft Docs"
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: b771194924fbd7757a356b119aa693eb46b3a17b
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="settings-waterfall"></a>设置瀑布图

设置瀑布图的概念意味着用户可以在“程序集”、“装置”和“浏览”级别指定设置： 

* 程序集 - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* 装置 - [PexClass](attribute-glossary.md#pexclass)
* 浏览 - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

在“程序集”级别上指定的设置会影响该程序集下的所有装置和浏览。 在“装置”级别上指定的设置会影响该装置下的所有浏览。 采用子设置的情况：如果在程序集和装置级别上定义了设置，则会使用装置中的设置。

请注意，某些设置特定于程序集级别或装置级别。 

**示例**

```
using Microsoft.Pex.Framework;

[assembly: PexAssemblySettings(MaxBranches = 1000)] // we override the default value of maxbranches

namespace MyTests
{
    [PexClass(MaxBranches = 500)] // we override the 1000 value and set maxbranches to 500 
    public partial class MyTests
    {
        [PexMethod(MaxBranches = 100)] // we override again, maxbranches = 100
        public void MyTest(...) { ... }
    }
}
```

## <a name="got-feedback"></a>是否获得反馈？

在 [UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest) 上发布想法和功能请求。
