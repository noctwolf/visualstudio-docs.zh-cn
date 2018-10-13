---
title: 从文本模板访问 Visual Studio 或其他主机 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a68886da-7416-4785-8145-3796bb382cba
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 3eb61ab5d372d02581c68391d125c7def23a402a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49298475"
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>从文本模板访问 Visual Studio 或其他主机
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在文本模板中，您可以使用方法和属性执行模板，如主机公开[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。  
  
 这适用于常规文本模板，不经过预处理的文本模板。  
  
## <a name="obtaining-access-to-the-host"></a>获取对主机的访问  
 设置`hostspecific="true"`在`template`指令。 这使您可以使用`this.Host`，其中包含类型<xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>。 此类型具有您可以使用，例如，若要解决文件的名称，并记录错误的成员。  
  
### <a name="resolving-file-names"></a>解析文件名称  
 若要查找相对于文本模板文件的完整路径，使用此。Host.ResolvePath()。  
  
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
  
### <a name="displaying-error-messages"></a>显示的错误消息  
 转换模板时，此示例中记录消息。 如果主机是[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]，添加到错误窗口。  
  
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
 如果在执行中的文本模板[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]，可以使用`this.Host`来访问服务提供的[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]的任何包或已加载的扩展。  
  
 设置 hostspecific ="true"，并强制转换`this.Host`到<xref:System.IServiceProvider>。  
  
 此示例将获取[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]API， <xref:EnvDTE.DTE>，作为一项服务：  
  
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
  
## <a name="using-hostspecific-with-template-inheritance"></a>使用模板继承 hostSpecific  
 指定`hostspecific="trueFromBase"`如果你还使用`inherits`属性，如果指定的模板继承`hostspecific="true"`。 这可以避免编译器警告的效果，属性`Host`具有已声明了两次。



