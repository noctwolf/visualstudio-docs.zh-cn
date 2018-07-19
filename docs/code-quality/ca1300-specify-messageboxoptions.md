---
title: CA1300：指定 MessageBoxOptions
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 815fe7b7f839adeb3204e33bb532b70909d92b53
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056382"
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300：指定 MessageBoxOptions

|||
|-|-|
|TypeName|SpecifyMessageBoxOptions|
|CheckId|CA1300|
|类别|Microsoft.Globalization|
|是否重大更改|非换行|

## <a name="cause"></a>原因

一个方法调用的重载<xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName>方法不采用<xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName>参数。

## <a name="rule-description"></a>规则说明

若要显示的区域性，使用从右到左的阅读顺序正确的消息框，请将传递[MessageBoxOptions.RightAlign](<xref:System.Windows.Forms.MessageBoxOptions.RightAlign>)并[MessageBoxOptions.RtlReading](<xref:System.Windows.Forms.MessageBoxOptions.RtlReading>)字段设置为<xref:System.Windows.Forms.MessageBox.Show%2A>方法。 检查<xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName>包含的控件，以确定是否使用从右到左的阅读顺序的属性。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请调用的重载<xref:System.Windows.Forms.MessageBox.Show%2A>方法采用<xref:System.Windows.Forms.MessageBoxOptions>参数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

它可以安全地禁止显示此规则的警告时不会使用从右到左阅读顺序的区域性本地化的代码库。

## <a name="example"></a>示例

下面的示例演示显示一个消息框，具有适用于区域性的阅读顺序的选项的方法。 所需的资源文件，而不会显示，若要生成示例。 按照此示例中生成该示例不使用资源文件，并要测试的从右到左功能中的注释。

[!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
[!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]

## <a name="see-also"></a>请参阅

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [桌面应用中的资源 (.NET Framework)](/dotnet/framework/resources/index)