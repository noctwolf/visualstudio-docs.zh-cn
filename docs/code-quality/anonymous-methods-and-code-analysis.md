---
title: 匿名方法的代码分析警告
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- methods, anonymous
- code analysis, anonymous methods
- anonymous methods, code analysis
ms.assetid: bf0a1a9b-b954-4d46-9c0b-cee65330ad00
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 47f90e0a9ca01e76ea1a3686c790dcf00a4becde
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53860775"
---
# <a name="anonymous-methods-and-code-analysis"></a>匿名方法和代码分析

*匿名方法*是没有名称的方法。 匿名方法最常用于将代码块作为委托参数传递。 本文介绍了代码分析警告和匿名方法的度量值的处理。

## <a name="anonymous-methods-declared-in-a-member"></a>在成员中声明的匿名方法

警告和成员，如方法或访问器中, 声明的匿名方法的指标与相关联的成员的声明的方法。 它们不会调用方法的成员与相关联。

例如，在下面的类的声明中找到的任何警告**anonymousMethod**应针对引发**Method1**而不**Method2**。

```vb
Delegate Function ADelegate(ByVal value As Integer) As Boolean

Class AClass
    Sub Method1()
        Dim anonymousMethod As ADelegate = Function(ByVal value As Integer) value > 5
        Method2(anonymousMethod)
    End Sub
    Sub Method2(ByVal anonymousMethod As ADelegate)
        anonymousMethod(10)
    End Sub
End Class
```

```csharp
delegate void Delegate();

class Class
{
    void Method1()
    {
        Delegate anonymousMethod = delegate()
        {
          Console.WriteLine("");
        }
        Method2(anonymousMethod);
    }

    void Method2(Delegate anonymousMethod)
    {
        anonymousMethod();
    }
}
```

## <a name="inline-anonymous-methods"></a>内联匿名方法

警告和被声明为内联的字段赋值的匿名方法的指标是与构造函数相关联。 如果该字段声明为`static`(`Shared`在 Visual Basic 中)，警告和度量值与相关联的类构造函数。 否则，它们与实例构造函数相关联。

例如，在下面的类的声明中找到的任何警告**anonymousMethod1**针对的隐式生成的默认构造函数将引发**类**。 在中找到的警告**anonymousMethod2**将适用于现用的隐式生成的类构造函数。

```vb
Delegate Function ADelegate(ByVal value As Integer) As Boolean
Class AClass
    Dim anonymousMethod1 As ADelegate = Function(ByVal value As Integer) value > 5
    Shared anonymousMethod2 As ADelegate = Function(ByVal value As Integer) value > 5

    Sub Method1()
        anonymousMethod1(10)
        anonymousMethod2(10)
    End Sub
End Class
```

```csharp
delegate void Delegate();

class Class
{
    Delegate anonymousMethod1 = delegate()
    {
       Console.WriteLine("");
    }

    static Delegate anonymousMethod2 = delegate()
    {
       Console.WriteLine("");
    }

    void Method()
    {
       anonymousMethod1();
       anonymousMethod2();
    }
}
```

类可以包含的内联匿名方法的值赋给具有多个构造函数的字段。 在这种情况下，警告和度量值与相关联的所有构造函数除非该构造函数链接到同一个类中的另一个构造函数。

例如，在下面的类的声明中找到的任何警告**anonymousMethod**应针对引发**Class(int)** 并**Class(string)**，但不是针对**Class()**。

```vb
Delegate Function ADelegate(ByVal value As Integer) As Boolean

Class AClass

    Dim anonymousMethod As ADelegate = Function(ByVal value As Integer) value > 5

    SubNew()
        New(CStr(Nothing))
    End Sub

    Sub New(ByVal a As Integer)
    End Sub

    Sub New(ByVal a As String)
    End Sub
End Class
```

```csharp
delegate void Delegate();

class Class
{
    Delegate anonymousMethod = delegate()
    {
       Console.WriteLine("");
    }

    Class() : this((string)null)
    {
    }

    Class(int a)
    {
    }

    Class(string a)
    {
    }
}
```

对构造函数会发出警告，因为编译器输出每个未链接到另一个构造函数的构造函数的唯一方法。 由于此行为，任何违反它将出现在**anonymousMethod**必须单独取消。 这还意味着，如果是新的构造函数中引入，已针对以前禁止显示警告**Class(int)** 并**Class(string)** 还必须取消对新的构造函数。

您可以解决此问题在两种方式之一：

- 声明**anonymousMethod**常见构造函数中的所有构造函数链。
- 声明**anonymousMethod**由所有构造函数调用的初始化方法中。

## <a name="see-also"></a>请参阅

- [分析托管代码质量](../code-quality/code-analysis-for-managed-code-overview.md)