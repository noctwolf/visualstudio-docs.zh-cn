---
title: '&lt;formRegions&gt;元素 （Visual Studio 中的 Office 开发）'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- formRegions element
- <formRegions> element
- application manifests [Office development in Visual Studio], <formRegions> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 36741e5e3bcd39dbb6e4ea0746e1877acc581e70
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2018
---
# <a name="ltformregionsgt-element-office-development-in-visual-studio"></a>&lt;formRegions&gt;元素 （Visual Studio 中的 Office 开发）
  `formRegions` 命名空间的 `vstov4` 元素包含与 VSTO 外接程序相关联的 Microsoft Office Outlook 窗体区域。  
  
## <a name="syntax"></a>语法  
  
```xml  
<formRegions>  
  <formRegion>  
  </formRegion>  
</formRegions>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `formRegions` 命名空间的 `vstov4` 元素包含 Outlook VSTO 外接程序的所有 `formRegion` 元素。 只有包括窗体区域的 Outlook VSTO 外接程序才需要该元素。  
  
 在应用程序清单中定义的 `formRegions` 元素可能只有一个。  
  
 `formRegions` 元素没有属性。  
  
 `formRegions` 元素具有以下元素。  
  
### <a name="formregion"></a>formRegion  
 为包含窗体区域的 Outlook VSTO 外接程序所需。 `formRegion`中定义了元素[ &#60;formRegion&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/formregion-element-office-development-in-visual-studio.md)。  
  
## <a name="vsto-add-in-example"></a>VSTO 外接程序示例  
  
### <a name="description"></a>描述  
 下面的代码示例演示应用程序级 Office 解决方案的应用程序清单中的 `formRegions` 元素，该解决方案是使用 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]部署的。 此代码示例摘自[Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)。  
  
### <a name="code"></a>代码  
  
```xml  
<vstov4:formRegions>  
  <vstov4:formRegion  
      name="OutlookAddIn1.FormRegion1">  
    <vstov4:messageClass name="IPM.Note" />  
    <vstov4:messageClass name="IPM.Contact" />  
    <vstov4:messageClass name="IPM.Appointment" />  
  </vstov4:formRegion>  
</vstov4:formRegions>  
```  
  
## <a name="see-also"></a>请参阅  
 [Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)   
 [部署 Office 解决方案的清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  