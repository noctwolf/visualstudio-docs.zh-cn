---
title: "示例 Excel 扩展：ExtensionPackage 类 | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 2d4c7b5c3aefbc59b8e8931376f0bcf14951c9bc
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="sample-excel-extension-extensionpackage-class"></a>示例 Excel 扩展：ExtensionPackage 类
此类扩展 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> 类，并为正在测试 [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] 工作表的编码的 UI 测试提供入口点。

## <a name="assembly-attribute"></a>程序集属性
 文件以程序集属性开头，此属性将此程序集标识为 UI 测试扩展。

```
[assembly: Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage(
    "ExcelExtensionPackage",
    typeof(
     Microsoft.VisualStudio.Test.Sample.UI.ExtensionPackage))]
```

 此属性声明自定义扩展包类的基类名称、包类的名称和完全限定的类名。

## <a name="simple-properties"></a>简单属性
 此类包含的属性的值供编码的 UI 测试框架用于标识和描述扩展和程序集。 有关详细信息，请参阅代码注释。

## <a name="getservice-method"></a>GetService 方法
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A> 方法是编码的 UI 测试框架使用的单一入口点（由每个对象的基类标识），用于访问技术管理器、属性提供程序和操作筛选器。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [扩展编码的 UI 测试和操作录制以支持 Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
