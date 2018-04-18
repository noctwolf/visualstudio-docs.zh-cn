---
title: CA1300： 指定 MessageBoxOptions |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
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
ms.workload:
- multiple
ms.openlocfilehash: 914654c5e2eee601ee2b314f15f5dfadb686c047
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300：指定 MessageBoxOptions
|||  
|-|-|  
|TypeName|SpecifyMessageBoxOptions|  
|CheckId|CA1300|  
|类别|Microsoft.Globalization|  
|是否重大更改|非重大|  
  
## <a name="cause"></a>原因  
 一个方法调用的重载<xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName>方法不采用<xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName>自变量。  
  
## <a name="rule-description"></a>规则说明  
 若要显示的区域性，使用从右到左阅读顺序，正确的消息框<xref:System.Windows.Forms.MessageBoxOptions>和<xref:System.Windows.Forms.MessageBoxOptions>的成员<xref:System.Windows.Forms.MessageBoxOptions>枚举必须传递给<xref:System.Windows.Forms.MessageBox.Show%2A>方法。 检查<xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName>要确定是否使用从右到左阅读顺序的包含控件的属性。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 若要修复与此规则的冲突，调用的重载<xref:System.Windows.Forms.MessageBox.Show%2A>采用的方法<xref:System.Windows.Forms.MessageBoxOptions>自变量。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 则可以安全地禁止显示此规则的警告时将不会使用从右到左阅读顺序区域性本地化代码库。  
  
## <a name="example"></a>示例  
 下面的示例演示的方法，显示的选项，适用于区域性的阅读顺序的消息框。 资源文件，而不会显示，需要将示例生成。 按照用于不使用资源文件将示例生成并测试从右到左功能的示例中的注释。  
  
 [!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
 [!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Resources.ResourceManager?displayProperty=fullName>   
 [桌面应用中的资源](/dotnet/framework/resources/index)