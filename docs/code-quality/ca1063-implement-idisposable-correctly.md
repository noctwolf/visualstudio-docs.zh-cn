---
title: CA1063:正确实现 IDisposable
ms.date: 02/12/2018
ms.topic: reference
f1_keywords:
- ImplementIDisposableCorrectly
- CA1063
helpviewer_keywords:
- CA1063
- ImplementIDisposableCorrectly
ms.assetid: 12afb1ea-3a17-4a3f-a1f0-fcdb853e2359
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: e4bc426162919f4112ffdfcc0fbeeb0fefd2f09e
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55945750"
---
# <a name="ca1063-implement-idisposable-correctly"></a>CA1063:正确实现 IDisposable

|||
|-|-|
|TypeName|ImplementIDisposableCorrectly|
|CheckId|CA1063|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因

<xref:System.IDisposable?displayProperty=nameWithType>接口的实现不正确。 可能的原因包括：

- <xref:System.IDisposable> 在类中重新实现。

- 最终确定 reoverridden。

- 重写 dispose （）。

- Dispose （） 方法不是公共的[密封](/dotnet/csharp/language-reference/keywords/sealed)，或已命名**Dispose**。

- Dispose （bool） 不受保护、 虚拟或未密封。

- 在未密封类型中，dispose （） 必须调用 dispose （true）。

- 对于非密封类型 Finalize 实现不会调用一个或两个 dispose （bool） 或基类的终结器。

冲突的任何一种模式触发警告 CA1063。

每个非密封的类型声明并实现<xref:System.IDisposable>接口必须提供其自己受保护的虚拟 void dispose （bool） 方法。 Dispose （） 应调用 Dipose(true)，和终结器应调用 dispose （false）。 如果您创建未密封的类型的声明并实现<xref:System.IDisposable>接口，必须定义 dispose （bool），调用它。 有关详细信息，请参阅[清理非托管资源 （.NET 指南）](/dotnet/standard/garbage-collection/unmanaged)并[Dispose 模式](/dotnet/standard/design-guidelines/dispose-pattern)。

## <a name="rule-description"></a>规则说明

所有<xref:System.IDisposable>的类型应该实现[Dispose 模式](/dotnet/standard/design-guidelines/dispose-pattern)正确。

## <a name="how-to-fix-violations"></a>如何解决冲突

检查你的代码并确定哪些以下解决方法将修复此冲突：

- 删除<xref:System.IDisposable>从列表中的由您的类型，实现，而是重写 Dispose 基类实现的接口。

- 根据您的类型中移除终结器，重写 Dispose (bool disposing)，其中 disposing 为 false 的代码路径中加入终结逻辑。

- 重写 Dispose (bool disposing)，并且其中 disposing 为 true 的代码路径中加入释放逻辑。

- 请确保 dispose （） 被声明为公共和[密封](/dotnet/csharp/language-reference/keywords/sealed)。

- 重命名为 dispose 方法**Dispose** ，并确保它被声明为公共和[密封](/dotnet/csharp/language-reference/keywords/sealed)。

- 请确保 dispose （bool） 声明为 protected、 virtual 和 unsealed。

- 修改 dispose （），使其调用 dispose （true），然后调用<xref:System.GC.SuppressFinalize%2A>上的当前对象实例 (`this`，或`Me`在 Visual Basic 中)，然后返回。

- 修改您终结器，使其调用 dispose （false），然后返回。

- 如果您创建未密封的类型的声明并实现<xref:System.IDisposable>接口，请确保实现<xref:System.IDisposable>遵循本部分前面所述的模式。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。

## <a name="pseudo-code-example"></a>伪代码示例

下面的伪代码提供了应如何使用托管的类中实现 dispose （bool） 和本机资源的常规示例。

```csharp
public class Resource : IDisposable
{
    private IntPtr nativeResource = Marshal.AllocHGlobal(100);
    private AnotherResource managedResource = new AnotherResource();

    // Dispose() calls Dispose(true)
    public void Dispose()
    {
        Dispose(true);
        GC.SuppressFinalize(this);
    }

    // NOTE: Leave out the finalizer altogether if this class doesn't
    // own unmanaged resources, but leave the other methods
    // exactly as they are.
    ~Resource()
    {
        // Finalizer calls Dispose(false)
        Dispose(false);
    }

    // The bulk of the clean-up code is implemented in Dispose(bool)
    protected virtual void Dispose(bool disposing)
    {
        if (disposing)
        {
            // free managed resources
            if (managedResource != null)
            {
                managedResource.Dispose();
                managedResource = null;
            }
        }
        // free native resources if there are any.
        if (nativeResource != IntPtr.Zero)
        {
            Marshal.FreeHGlobal(nativeResource);
            nativeResource = IntPtr.Zero;
        }
    }
}
```

## <a name="see-also"></a>请参阅

- [释放模式 （framework 设计准则）](/dotnet/standard/design-guidelines/dispose-pattern)
- [清理非托管资源 （.NET 指南）](/dotnet/standard/garbage-collection/unmanaged)