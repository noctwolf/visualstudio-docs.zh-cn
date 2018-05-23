---
title: '&lt;文档&gt;元素 （Visual Studio 中的 Office 开发）'
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
ms.openlocfilehash: 07d8172ec4e56352c2244aef02d947ac48833ab7
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2018
---
# <a name="ltdocumentgt-element-office-development-in-visual-studio"></a>&lt;文档&gt;元素 （Visual Studio 中的 Office 开发）
  `document`元素`vstov4`命名空间存储文档级自定义的自定义项特定信息。  
  
## <a name="syntax"></a>语法  
  
```xml  
<document solutionId />  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 仅对文档级自定义项必需。 `document`元素处于`vstov4`命名空间。 `document`元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`solutionId`|必须的。 Visual Studio Tools for Office 运行时用于唯一标识的文档级解决方案的 GUID。 此值存储为 _AssemblyLocation 自定义文档属性。 有关详细信息，请参阅[自定义文档属性概述](../vsto/custom-document-properties-overview.md)。|  
  
 `document` 不包含任何子元素。  
  
## <a name="document-level-customization-example"></a>文档级自定义项示例  
  
### <a name="description"></a>描述  
 下面的代码示例阐释了`document`通过使用部署的文档级 Office 解决方案中的元素[!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]。 此代码示例摘自[Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)。  
  
### <a name="code"></a>代码  
  
```xml
<vstov4:document   
  solutionId="73e" />  
```  
  
## <a name="see-also"></a>请参阅  
 [Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)   
 [部署 Office 解决方案的清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  