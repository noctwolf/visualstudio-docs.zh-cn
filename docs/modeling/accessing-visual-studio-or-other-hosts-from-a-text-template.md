---
title: 从文本模板访问 Visual Studio 或其他主机
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 657abba976e0f0d167651943289296d340981e62
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="access-visual-studio-or-other-hosts-from-a-text-template"></a>从文本模板访问 Visual Studio 或其他主机

在一个文本模板，你可以使用方法和执行模板主机公开的属性。 Visual Studio 是宿主的一个示例。

> [!NOTE]
> 在正则文本模板，但不是在你可以使用主机方法和属性*预处理*文本模板。

## <a name="obtain-access-to-the-host"></a>获取对主机访问权限

若要访问主机，设置`hostspecific="true"`中`template`指令。 现在，你可以使用`this.Host`，具有类型<xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>。 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>类型具有可用于，例如，解析文件名称并记录错误的成员。

### <a name="resolve-file-names"></a>解析文件名称

若要查找相对于文本模板文件的完整路径，使用`this.Host.ResolvePath()`。

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.IO" #>
<#
 // Find a path within the same project as the text template:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of myFile is:
<#= myFile #>
```

### <a name="display-error-messages"></a>显示错误消息

当你转换模板时，此示例将记录的消息。 如果主机是 Visual Studio，将错误添加到**错误列表**。

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.CodeDom.Compiler" #>
<#
  string message = "test message";
  this.Host.LogErrors(new CompilerErrorCollection()
    { new CompilerError(
       this.Host.TemplateFile, // Identify the source of the error.
       0, 0, "0",   // Line, column, error ID.
       message) }); // Message displayed in error window.
#>
```

## <a name="use-the-visual-studio-api"></a>使用 Visual Studio API

如果你要在 Visual Studio 中执行文本模板时，你可以使用`this.Host`由 Visual Studio 和任何包或加载的扩展提供的访问服务。

设置 hostspecific ="true"，并强制转换`this.Host`到<xref:System.IServiceProvider>。

此示例将获取 Visual Studio API， <xref:EnvDTE.DTE>，作为一项服务：

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="EnvDTE" #>
<#
 IServiceProvider serviceProvider = (IServiceProvider)this.Host;
 DTE dte = serviceProvider.GetService(typeof(DTE)) as DTE;
#>
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>
```

## <a name="use-hostspecific-with-template-inheritance"></a>HostSpecific 使用模板继承

指定`hostspecific="trueFromBase"`如果你还使用`inherits`属性，如果从指定的模板继承和`hostspecific="true"`。 如果不这样做，可能会编译器警告，属性`Host`已两次声明。