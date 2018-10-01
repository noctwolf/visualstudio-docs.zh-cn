---
title: 从文本模板访问模型 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, accessing models
ms.assetid: cf65395a-0ca3-4826-89c7-b1869562685c
caps.latest.revision: 35
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 5f23a080f33b668d185f4e7b1409da5b4ac97deb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479468"
---
# <a name="accessing-models-from-text-templates"></a>从文本模板访问模型
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[从文本模板访问模型](https://docs.microsoft.com/visualstudio/modeling/accessing-models-from-text-templates)。  
  
通过使用文本模板，可以创建报表文件、 源代码文件和其他基于特定于域的语言模型的文本文件。 有关文本模板的基本信息，请参阅[代码生成和 T4 文本模板](../modeling/code-generation-and-t4-text-templates.md)。 文本模板时你正在调试你的 DSL 中，将在实验模式下工作，还将具有在其部署 DSL 的计算机上工作。  
  
> [!NOTE]
>  创建 DSL 解决方案、 示例文本模板时 **\*.tt**调试的项目中生成文件。 当您更改的域类的名称时，这些模板将不再起作用。 然而，它们包括所需的基本指令，并且提供了示例，可以更新以匹配你的 DSL。  
  
 若要从文本模板访问模型：  
  
-   设置为 template 指令的继承属性<xref:Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation>。 这提供对应用商店的访问。  
  
-   指定你想要访问 DSL 的指令处理器。 这将加载用于 DSL 的程序集，以便可以在文本模板的代码中使用其域类、 属性和关系。 它还会加载您指定的模型文件。  
  
 一个`.tt`时创建一个新的调试项目中创建类似于下面的示例文件[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]从 DSL 最小语言模板的解决方案。  
  
```  
<#@ template inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>  
<#@ output extension=".txt" #>  
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>  
  
This text will be output directly.  
  
This is the name of the model: <#= this.ModelRoot.Name #>  
  
Here is a list of elements in the model:  
<#  
  // When you change the DSL Definition, some of the code below may not work.  
  foreach (ExampleElement element in this.ExampleModel.Elements)  
  {#>  
<#= element.Name #>  
<#      
  }  
#>  
  
```  
  
 请注意，此模板有关的以下几点：  
  
-   域类、 属性和在 DSL 定义中定义的关系，可以使用该模板。  
  
-   加载模板中指定的模型文件`requires`属性。  
  
-   中的属性`this`包含根元素。 在这里，你的代码可以导航到模型的其他元素。 属性的名称通常是与你的 DSL 的根域类相同。 在此示例中，设为 `this.ExampleModel`。  
  
-   尽管编写的代码片段所用的语言为 C#，可以生成任何类型的文本。 或者可以在编写代码[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]属性添加`language="VB"`到`template`指令。  
  
-   若要调试该模板，添加`debug="true"`到`template`指令。 该模板将在另一个实例中打开[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]如果发生异常。 如果你想要在代码中的特定点在调试器中中断，insert 语句 `System.Diagnostics.Debugger.Break();`  
  
     有关详细信息，请参阅[调试 T4 文本模板](../modeling/debugging-a-t4-text-template.md)。  
  
## <a name="about-the-dsl-directive-processor"></a>有关 DSL 的指令处理器  
 该模板可以使用 DSL 定义中定义的域类。 这使通常会显示该模板的起点附近的指令。 在上一示例中，它是以下。  
  
```  
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>  
```  
  
 指令的名称 ( `MyLanguage`，在此示例中) 派生自你的 DSL 的名称。 它将调用*指令处理器*生成你的 DSL 的一部分。 您可以找到在其源代码**Dsl\GeneratedCode\DirectiveProcessor.cs**。  
  
 DSL 的指令处理器将执行两个主要任务：  
  
-   它有效地将程序集和导入指令插入到模板中引用你的 DSL。 这样可以在模板代码中使用域类。  
  
-   它将加载在指定的文件`requires`参数，并且设置属性`this`，是指加载模型的根元素。  
  
## <a name="validating-the-model-before-running-the-template"></a>在运行该模板之前验证模型  
 您可能会导致执行该模板之前要验证的模型。  
  
```  
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1';validation='open|load|save|menu'" #>  
  
```  
  
 请注意：  
  
1.  `filename`和`validation`参数分隔与";"，且必须具有其他分隔符或空格。  
  
2.  验证类别列表确定将执行的验证方法。 应使用分隔多个类别"&#124;"，且必须具有其他分隔符或空格。  
  
 如果找到错误，则它将在错误窗口中，报告和结果文件将包含一条错误消息。  
  
##  <a name="Multiple"></a> 从文本模板访问多个模型  
  
> [!NOTE]
>  此方法允许你读取同一模板中的多个模型，但不支持 ModelBus 引用。 若要读取的 ModelBus 引用连接符的模型，请参阅[文本模板中使用 Visual Studio ModelBus](../modeling/using-visual-studio-modelbus-in-a-text-template.md)。  
  
 如果你想要从相同的文本模板访问多个模型，则必须调用生成的指令处理器一次为每个模型。 必须指定每个模型中的文件名称`requires`参数。 必须指定要用于中的根域类的名称`provides`参数。 必须指定不同的值`provides`中每个指令调用的参数。 例如，假定您有三个名为 Library.xyz、 School.xyz 和 Work.xyz 的模型文件。 若要从相同的文本模板访问它们，必须编写类似于以下的三个指令调用。  
  
```  
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Library.xyz'" provides="ExampleModel=LibraryModel" #>  
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='School.xyz'" provides="ExampleModel=SchoolModel" #>  
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Work.xyz'" provides="ExampleModel=WorkModel" #>  
```  
  
> [!NOTE]
>  此示例代码是一种语言，根据最小语言解决方案模板。  
  
 若要访问在文本模板中的模型，现在可以在下面的示例中编写代码的代码相似。  
  
```csharp  
<#  
foreach (ExampleElement element in this.LibraryModel.Elements)  
...  
foreach (ExampleElement element in this.SchoolModel.Elements)  
...  
foreach (ExampleElement element in this.WorkModel.Elements)  
...  
#>  
```  
  
```vb  
<#  
For Each element As ExampleElement In Me.LibraryModel.Elements  
...  
For Each element As ExampleElement In Me.SchoolModel.Elements  
...  
For Each element As ExampleElement In Me.WorkModel.Elements  
...  
#>  
```  
  
## <a name="loading-models-dynamically"></a>动态加载模型  
 如果你想要在运行时确定要加载的模型，可以在程序代码中，而不是使用特定于 DSL 的指令动态加载模型文件。  
  
 但是，特定于 DSL 的函数之一是指令的导入 DSL 的命名空间，以便在将模板代码可以使用该 DSL 中定义的域类。 由于不使用该指令，因此必须添加**\<程序集 >** 并**\<导入 >** 指令可能会加载的所有模型。 这非常简单，如果可能会加载不同的模型是相同的 DSL 的所有实例。  
  
 若要加载该文件，最有效方法是使用[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]ModelBus。 在典型方案中，文本模板将使用特定于 DSL 的指令以常规方式加载的第一个模型。 该模型将包含到另一个模型的 ModelBus 引用。 可以使用 ModelBus 打开被引用的模型和访问特定元素。 有关详细信息，请参阅[文本模板中使用 Visual Studio ModelBus](../modeling/using-visual-studio-modelbus-in-a-text-template.md)。  
  
 在不太常用的方案中，你可能想要打开模型文件必须仅文件名，这可能不会在当前和[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]项目。 在这种情况下，可以打开该文件使用的方法中所述[如何： 从程序代码中的文件打开模型](../modeling/how-to-open-a-model-from-file-in-program-code.md)。  
  
## <a name="generating-multiple-files-from-a-template"></a>从模板生成多个文件  
 如果你想要生成多个文件-例如，若要在模型中，生成一个单独的文件的每个元素有几个可能的实现方式。 默认情况下，只有一个文件生成从每个模板文件。  
  
### <a name="splitting-a-long-file"></a>拆分长文件  
 在此方法中，使用模板来生成一个文件中，由分隔符分隔。 然后将文件拆分为各个部分。 有两个模板; 一个用于生成单文件，另一个用于将其拆分。  
  
 **LoopTemplate.t4**生成很长的单个文件。 请注意其文件扩展名为".t4"，因为它不应处理直接在您单击**转换所有模板**。 此模板将采用的参数，指定用于分隔段的分隔符字符串：  
  
```  
<#@ template ninherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>  
<#@ parameter name="delimiter" type="System.String" #>  
<#@ output extension=".txt" #>  
<#@ MyDSL processor="MyDSLDirectiveProcessor" requires="fileName='SampleModel.mydsl1';validation='open|load|save|menu'" #>  
<#  
  // Create a file segment for each element:  
  foreach (ExampleElement element in this.ExampleModel.Elements)   
  {   
    // First item is the delimiter:  
#>  
<#= string.Format(delimiter, element.Id) #>  
  
   Element: <#= element.Name #>  
<#  
   // Here you generate more content derived from the element.  
  }  
#>  
  
```  
  
 `LoopSplitter.tt` 调用`LoopTemplate.t4`，然后将生成的文件拆分为其段和。 请注意，此模板没有已建模的模板，因为它不会读取模型。  
  
```  
<#@ template hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ import namespace="Microsoft.VisualStudio.TextTemplating" #>  
<#@ import namespace="System.Runtime.Remoting.Messaging" #>  
<#@ import namespace="System.IO" #>  
  
<#  
  // Get the local path:  
  string itemTemplatePath = this.Host.ResolvePath("LoopTemplate.t4");  
  string dir = Path.GetDirectoryName(itemTemplatePath);  
  
  // Get the template for generating each file:  
  string loopTemplate = File.ReadAllText(itemTemplatePath);  
  
  Engine engine = new Engine();  
  
  // Pass parameter to new template:  
  string delimiterGuid = Guid.NewGuid().ToString();  
  string delimiter = "::::" + delimiterGuid + ":::";  
  CallContext.LogicalSetData("delimiter", delimiter + "{0}:::");   
  string joinedFiles = engine.ProcessTemplate(loopTemplate, this.Host);  
  
  string [] separateFiles = joinedFiles.Split(new string [] {delimiter}, StringSplitOptions.None);  
  
  foreach (string nameAndFile in separateFiles)   
  {   
     if (string.IsNullOrWhiteSpace(nameAndFile)) continue;  
     string[] parts = nameAndFile.Split(new string[]{":::"}, 2, StringSplitOptions.None);  
     if (parts.Length < 2) continue;  
#>  
 Generate: [<#= dir #>] [<#= parts[0] #>]  
<#  
     // Generate a file from this item:  
     File.WriteAllText(Path.Combine(dir, parts[0] + ".txt"), parts[1]);    
  }  
#>  
  
```



