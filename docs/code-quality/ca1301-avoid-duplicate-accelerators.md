---
title: CA1301:避免快捷键重复
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1301
- AvoidDuplicateAccelerators
helpviewer_keywords:
- CA1301
- AvoidDuplicateAccelerators
ms.assetid: 20570a00-864b-459c-a1fa-a6e9db5f1001
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f82163b1c377df4c8c7fcbba07672312153dad9b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62797480"
---
# <a name="ca1301-avoid-duplicate-accelerators"></a>CA1301:避免快捷键重复

|||
|-|-|
|TypeName|AvoidDuplicateAccelerators|
|CheckId|CA1301|
|类别|Microsoft.Globalization|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 类型扩展<xref:System.Windows.Forms.Control?displayProperty=fullName>和包含两个或多个具有相同的访问密钥存储在资源文件中的顶级控件。

## <a name="rule-description"></a>规则说明

访问密钥，也称为快捷键，允许使用的键盘访问控件**Alt**密钥。 如果多个控件具有相同的访问密钥，不是定义完善的访问密钥的行为。 用户可能无法再访问目标的控件使用的访问密钥，并且可能会启用旨在以外的控件。

此规则的当前实现将忽略菜单项。 但是，相同的子菜单中的菜单项不应具有相同的访问密钥。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请定义所有控件的唯一访问的密钥。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示一个包含具有相同的访问键的两个控件的最小窗体。 密钥存储在资源文件中，而不会显示。 但是，其值显示在注释掉`checkBox.Text`行。 可以通过交换检查的快捷键重复行为`checkBox.Text`具有对应的注释掉的行。 但是，在这种情况下，该示例不会生成警告规则。

 [!code-csharp[FxCop.Globalization.AvoidDuplicateAccels#1](../code-quality/codesnippet/CSharp/ca1301-avoid-duplicate-accelerators_1.cs)]

## <a name="see-also"></a>请参阅

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [桌面应用中的资源](/dotnet/framework/resources/index)