---
title: CA2007:不直接等待任务
ms.date: 03/08/2019
ms.topic: reference
f1_keywords:
- CA2007
- DoNotDirectlyAwaitATaskAnalyzer
helpviewer_keywords:
- CA2007
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.openlocfilehash: 8e94b67d1924e2144f658cd6bcd5989751efdb85
ms.sourcegitcommit: 1024f336dcd8e8a4c50b9a9ad8ec85b6e70073a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57699676"
---
# <a name="ca2007-do-not-directly-await-a-task"></a>CA2007:不直接等待任务

|||
|-|-|
|TypeName|DoNotDirectlyAwaitATaskAnalyzer|
|CheckId|CA2007|
|类别|Microsoft.Reliability|
|是否重大更改|非换行|

## <a name="cause"></a>原因

异步方法[等待](/dotnet/csharp/language-reference/keywords/await)<xref:System.Threading.Tasks.Task>直接。

## <a name="rule-description"></a>规则说明

当异步方法等待<xref:System.Threading.Tasks.Task>延续直接创建了任务的同一线程中发生。 此行为可以极大地降低性能，并且可能会导致在 UI 线程上发生死锁。 请考虑调用<xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType>以指示您的继续符的意图。

此规则随[FxCop 分析器](install-fxcop-analyzers.md)"旧"（静态代码分析） 中不存在和 FxCop。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要解决冲突，请调用<xref:System.Threading.Tasks.Task.ConfigureAwait%2A>上等待<xref:System.Threading.Tasks.Task>。 您可以传递`true`或`false`为`continueOnCapturedContext`参数。

- 调用`ConfigureAwait(true)`任务上具有相同的行为不显式调用<xref:System.Threading.Tasks.Task.ConfigureAwait%2A>。 通过显式调用此方法，即让读者了解有意想要在原始的同步上下文上执行延续任务。

- 调用`ConfigureAwait(false)`来计划到线程池的延续任务，从而避免在 UI 线程上的发生死锁。 传递`false`是独立于应用程序的库的一个不错的选择。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

如果您知道，使用者不是一个图形用户界面 (GUI) 应用，或使用者没有可以取消显示此警告<xref:System.Threading.SynchronizationContext>。

## <a name="example"></a>示例

下面的代码段将生成警告：

```csharp
public async Task Execute()
{
    Task task = null;
    await task;
}
```

若要解决冲突，请调用<xref:System.Threading.Tasks.Task.ConfigureAwait%2A>上等待<xref:System.Threading.Tasks.Task>:

```csharp
public async Task Execute()
{
    Task task = null;
    await task.ConfigureAwait(false);
}
```

## <a name="see-also"></a>请参阅

- [应等待的任务使用 configureawait （false）？](https://github.com/Microsoft/vs-threading/blob/master/doc/cookbook_vs.md#should-i-await-a-task-with-configureawaitfalse)
- [在 Visual Studio 中安装 FxCop 分析器](install-fxcop-analyzers.md)