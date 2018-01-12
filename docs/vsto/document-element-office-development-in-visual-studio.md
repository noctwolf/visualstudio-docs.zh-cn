---
title: "&lt;文档&gt;元素 （Visual Studio 中的 Office 开发） |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document element
- application manifests [Office development in Visual Studio], <document> element
- <document> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 38b03c2a4980891d9a6841b24365db32ee555de4
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
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
  
 `document`不包含任何子元素。  
  
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
  
  