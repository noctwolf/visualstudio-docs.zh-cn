---
title: 设置瀑布图 | Microsoft IntelliTest 开发人员测试工具 | Microsoft Docs
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 9265fd0ada4f966f5d5fba01591e10f5f0a4194f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
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
