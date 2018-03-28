---
title: 在 Visual Studio 中生成使用 TextTransform 实用工具的文件 |Microsoft 文档
ms.date: 03/22/2018
ms.topic: article
helpviewer_keywords:
- text templates, TextTransform utility
- TextTransform.exe
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 5ecc5af3c37889bc79dc5978c33caf8249433978
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="generate-files-with-the-texttransform-utility"></a>生成使用 TextTransform 实用工具的文件

TextTransform.exe 是一个命令行工具，可用于转换文本模板。 在调用 TextTransform.exe 时，你作为自变量指定的文本模板文件的名称。 TextTransform.exe 调用文本转换引擎，并处理文本模板。 TextTransform.exe 通常从脚本调用。 但是，它不是通常是必需的因为 Visual Studio 中或在生成过程中，您可以执行文本转换。

> [!NOTE]
> 如果你想要执行文本转换为生成过程的一部分，请考虑使用 MSBuild 文本转换任务。 有关详细信息，请参阅[生成过程中的代码生成](../modeling/code-generation-in-a-build-process.md)。 中的计算机上[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]已安装，你还可以编写应用程序或[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]可以转换文本模板的扩展。 有关详细信息，请参阅[使用自定义宿主处理文本模板](../modeling/processing-text-templates-by-using-a-custom-host.md)。

 TextTransform.exe 位于以下目录：

 **\Program Files (x86)\Microsoft Visual Studio\2017\Professional\Common7\IDE**

专业版中，或

 **\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**

 用于 Enterprise edition 中。

在以前版本的 Visual Studio 中，在以下位置找到该文件：

**\Program Files (x86)\Common Files\Microsoft Shared\TextTemplating\{version}**

其中 {版本} 取决于所安装的上一个版本。

## <a name="syntax"></a>语法

```
TextTransform [<options>] <templateName>
```

### <a name="parameters"></a>参数

|**参数**|**说明**|
|------------------|---------------------|
|`templateName`|标识你想要转换的模板文件的名称。|

|**选项**|**说明**|
|----------------|---------------------|
|**-out** \<filename>|所转换的输出写入到文件。|
|**-r** \<assembly>|程序集，用于编译和运行文本模板。|
|**-u** \<namespace>|用于编译模板命名空间。|
|**-I** \<includedirectory>|包含指定的文本模板中包括的文本模板的目录。|
|**-P** \<referencepath>|要搜索的文本模板中指定的程序集或使用目录**-r**选项。<br /><br /> 例如，若要包括用于 Visual Studio API 的程序集，使用<br /><br /> `-P "%VSSHELLFOLDER%\Common7\IDE\PublicAssemblies"`|
|**-dp** \<processorName>!\<className>!\<assemblyName&#124;codeBase>|名称、 完整类型名称和可以用于处理文本模板中的自定义指令的指令处理器的程序集。|
|**-a** [processorName]![directiveName]!\<parameterName>!\<parameterValue>|指定指令处理器的参数值。 如果你指定只需的参数名称和值，该参数将可供所有指令处理器。 如果指定指令处理器，参数是仅供指定的处理器。 如果指定指令的名称，仅当正在处理指定的指令参数才可用。<br /><br /> 若要访问从指令处理器或文本模板的参数值，使用[ITextTemplatingEngineHost.ResolveParameterValue](https://msdn.microsoft.com/library/microsoft.visualstudio.texttemplating.itexttemplatingenginehost.resolveparametervalue.aspx)。 在文本模板中，包括`hostspecific`的 template 指令中并调用消息`this.Host`。 例如：<br /><br /> `<#@template language="c#" hostspecific="true"#> [<#= this.Host.ResolveParameterValue("", "", "parameterName") #>]`。<br /><br /> 始终键入 ！ 将标记，即使你省略了可选的处理器和指令的名称。 例如：<br /><br /> `-a !!param!value`|
|**-h**|提供帮助。|

## <a name="related-topics"></a>相关主题

|任务|主题|
|----------|-----------|
|在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 解决方案中生成文件。|[使用 T4 文本模板生成设计时代码](../modeling/design-time-code-generation-by-using-t4-text-templates.md)|
|编写指令处理器转换自己的数据源。|[自定义 T4 文本转换](../modeling/customizing-t4-text-transformation.md)|
|编写文本模板化主机，您可以调用自己的应用程序从文本模板。|[使用自定义宿主处理文本模板](../modeling/processing-text-templates-by-using-a-custom-host.md)|