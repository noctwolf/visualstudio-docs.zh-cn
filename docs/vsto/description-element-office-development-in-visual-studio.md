---
title: '&lt;说明&gt;元素 （Visual Studio 中的 Office 开发）'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- description element
- <description> element
- application manifests [Office development in Visual Studio], <description> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9fcdac1e950d98394b5703322f40dd1823b246f6
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34265110"
---
# <a name="ltdescriptiongt-element-office-development-in-visual-studio"></a>&lt;说明&gt;元素 （Visual Studio 中的 Office 开发）
  `description` 命名空间的 `vstov4` 元素会存储在 Microsoft Office 应用程序的 COM 加载项对话框中显示的 Office 解决方案说明。  
  
## <a name="syntax"></a>语法  
  
```xml  
<description>  
</description>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 可选。 `description` 元素位于 `vstov4` 命名空间中。 它包含在 Microsoft Office 应用程序中的 COM 加载项对话框中显示的加载项说明。  
  
 `description` 元素没有属性或元素。  
  
## <a name="vsto-add-in-example"></a>VSTO 外接程序示例  
  
### <a name="description"></a>描述  
 下面的代码示例演示使用 `description` 部署的应用程序级解决方案的 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]元素。 此代码示例摘自[Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)。  
  
### <a name="code"></a>代码  
  
```xml  
<vstov4:description>  
  ContosoOutlookAddIn - Outlook add-in   
  created with Visual Studio Tools for Office  
</vstov4:description>  
```  
  
## <a name="see-also"></a>请参阅  
 [Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)   
 [部署 Office 解决方案的清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  