---
title: "如何： 使用转义序列从模板生成模板 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, generating templates from templates
ms.assetid: 4126156a-7cea-48b8-925e-7790806cfe6c
caps.latest.revision: "35"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 634d5617d1f42891953f8f1a73bcc5d09a8ffa9b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-generate-templates-from-templates-by-using-escape-sequences"></a>如何：使用转义序列从模板生成模板
你可以创建用于创建为其生成的文本输出的另一个文本模板的文本模板。 若要执行此操作，必须使用转义序列来描述文本模板标记。 如果不使用转义序列，生成的文本模板将具有预定义的含义。 有关在文本模板中使用转义序列的详细信息，请参阅[文本模板中使用转义序列](../modeling/using-escape-sequences-in-text-templates.md)。  
  
### <a name="to-generate-a-text-template-from-within-a-text-template"></a>若要生成在文本模板中的文本模板  
  
-   使用反斜杠 (\\) 作为转义符可以生成必需的指令、 语句、 表达式文本模板中的标记和类中的单独的文本模板文件的功能。  
  
    ```  
    \<#@ directive \#>  
    \<# statement \#>  
    \<#= expression \#>  
    \<#+ classfeature \#>  
    ```  
  
## <a name="example"></a>示例  
 下面的示例使用转义字符来生成文本模板中的文本模板。 `output`指令为文本模板文件类型 (.tt) 设置目标文件类型。  
  
```csharp  
\<#@ output extension=".tt" \#>  
\<#@ assembly name="System.Xml.dll" \#>  
\<#@ import namespace="System.Xml" \#>  
\<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {\#>  
           \<#= attr.Name \#>  
       \<#}  
     }  
\#>  
```  
  
 生成的文本输出是一个文本模板。  
  
```  
<#@ output extension=".tt" #>  
<#@ assembly name="System.Xml.dll" #>  
<#@ import namespace="System.Xml" #>  
<#  
XmlDocument xDoc = new XmlDocument();  
//System.Diagnostics.Debugger.Break();  
    xDoc.Load(@"E:\CSharp\Overview.xml");  
    XmlAttributeCollection attributes = xDoc.Attributes;  
    if (attributes != null)  
    {  
       foreach (XmlAttribute attr in attributes)  
       {#>  
           <#= attr.Name #>  
       <#}  
     }  
#>  
```