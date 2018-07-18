---
title: CA1016：用 AssemblyVersionAttribute 标记程序集
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkAssembliesWithAssemblyVersion
- CA1016
helpviewer_keywords:
- CA1016
- MarkAssembliesWithAssemblyVersion
ms.assetid: 4340aed8-d92b-4cde-a398-cb6963c6da5a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3080b5a45f61010f322ed183a8b5a7c23390de33
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31897413"
---
# <a name="ca1016-mark-assemblies-with-assemblyversionattribute"></a>CA1016：用 AssemblyVersionAttribute 标记程序集
|||
|-|-|
|TypeName|MarkAssembliesWithAssemblyVersion|
|CheckId|CA1016|
|类别|Microsoft.Design|
|是否重大更改|非重大|

## <a name="cause"></a>原因
 程序集没有版本号。

## <a name="rule-description"></a>规则说明
 程序集的标识组成的以下信息：

-   程序集名称

-   版本号

-   culture

-   （对于强名称程序集） 的公钥。

 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 使用版本号唯一地标识程序集，并绑定到具有强名称的程序集中的类型。 版本号与版本和发行者策略一起使用。 默认情况下，仅使用用于生成应用程序的程序集版本运行应用程序。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，版本号的程序集使用添加<xref:System.Reflection.AssemblyVersionAttribute?displayProperty=fullName>属性。 请参见以下示例。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不要禁止此规则的警告显示有关由第三方，或在生产环境中使用的程序集。

## <a name="example"></a>示例
 下面的示例演示具有的程序集<xref:System.Reflection.AssemblyVersionAttribute>应用的属性。

 [!code-csharp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CSharp/ca1016-mark-assemblies-with-assemblyversionattribute_1.cs)]
 [!code-vb[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/VisualBasic/ca1016-mark-assemblies-with-assemblyversionattribute_1.vb)]
 [!code-cpp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CPP/ca1016-mark-assemblies-with-assemblyversionattribute_1.cpp)]

## <a name="see-also"></a>请参阅
 [程序集版本控制](/dotnet/framework/app-domains/assembly-versioning)[如何： 创建发行者策略](/dotnet/framework/configure-apps/how-to-create-a-publisher-policy)