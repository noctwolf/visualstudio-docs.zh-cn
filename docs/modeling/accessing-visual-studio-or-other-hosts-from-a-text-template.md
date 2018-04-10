---
title: 从文本模板访问 Visual Studio 或其他主机 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: cd72a2838e9dd7a903e5cf76aac30e2922708872
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2018
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>从文本模板访问 Visual Studio 或其他主机
在一个文本模板，你可以使用方法和属性公开主机执行该模板后，如[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。  
  
 这适用于常规文本模板，不进行预处理的文本模板。  
  
## <a name="obtaining-access-to-the-host"></a>获取对主机的访问  
 设置`hostspecific="true"`中`template`指令。 这样便可以使用`this.Host`，具有类型<xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>。 此类型具有可以使用，例如，解析文件名以及记录错误的成员。  
  
### <a name="resolving-file-names"></a>解析文件名称  
 若要查找相对于文本模板文件的完整路径，请使用此。Host.ResolvePath()。  
  
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
  
### <a name="displaying-error-messages"></a>显示错误消息  
 当你转换模板时，此示例将记录的消息。 如果主机是[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，它们添加到错误窗口。  
  
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
  
## <a name="using-the-visual-studio-api"></a>使用 Visual Studio API  
 如果在执行中的文本模板[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]，你可以使用`this.Host`访问服务提供的[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]以及任何包或加载的扩展。  
  
 设置 hostspecific ="true"，并强制转换`this.Host`到<xref:System.IServiceProvider>。  
  
 此示例将获取[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]API， <xref:EnvDTE.DTE>，作为一项服务：  
  
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
  
## <a name="using-hostspecific-with-template-inheritance"></a>HostSpecific 使用模板继承  
 指定`hostspecific="trueFromBase"`如果你还使用`inherits`属性，如果从指定的模板继承和`hostspecific="true"`。 这样就避免了编译器警告的效果，属性`Host`已两次声明。