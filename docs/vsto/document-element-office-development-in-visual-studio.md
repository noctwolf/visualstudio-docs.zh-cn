---
title: '&lt;文档&gt;元素 （Visual Studio 中的 Office 开发） |Microsoft 文档'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document element
- application manifests [Office development in Visual Studio], <document> element
- <document> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0e33e638937a02589a08e3ba2bebf9d3e9aeb1a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ltdocumentgt-element-office-development-in-visual-studio"></a>&lt;文档&gt;元素 （Visual Studio 中的 Office 开发）
  `document`元素`vstov4`命名空间存储文档级自定义的自定义项特定信息。  
  
## <a name="syntax"></a>语法  
  
```  
<document solutionId />  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 仅对文档级自定义项必需。 `document`元素处于`vstov4`命名空间。 `document`元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`solutionId`|必须的。 Visual Studio Tools for Office 运行时用于唯一标识的文档级解决方案的 GUID。 此值存储为 _AssemblyLocation 自定义文档属性。 有关更多信息，请参见 [Custom Document Properties Overview](../vsto/custom-document-properties-overview.md)。|  
  
 `document` 不包含任何子元素。  
  
## <a name="document-level-customization-example"></a>文档级自定义项示例  
  
### <a name="description"></a>描述  
 下面的代码示例阐释了`document`通过使用部署的文档级 Office 解决方案中的元素[!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]。 此代码示例摘自 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中提供的一个更大的示例。  
  
### <a name="code"></a>代码  
  
```  
<vstov4:document   
  solutionId="73e" />  
```  
  
## <a name="see-also"></a>请参阅  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  