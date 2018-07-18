---
title: '&lt;appAddin&gt;元素 （Visual Studio 中的 Office 开发）'
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <appAddin> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0defe437e0778ee9d3c134148a3ca7e4b4cd2ef9
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2018
ms.locfileid: "34264657"
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;appAddin&gt;元素 （Visual Studio 中的 Office 开发）
  **AppAddin**元素`vstov4`命名空间存储 VSTO 外接程序的自定义项特定信息。  
  
## <a name="syntax"></a>语法  
  
```xml 
<appAddin  
  application  
  loadBehavior  
  keyName>  
  <friendlyName>  
  <description>  
  <formRegions></formRegions>  
</appAddin>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 **AppAddin**元素是必需的它位于`vstov4`命名空间。 只有一个**appAddin**应用程序清单中定义的元素。  
  
 **AppAddin**元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|**应用程序**|必须的。 标识 Microsoft Office 应用程序。 值可以是以下值之一：Excel、InfoPath、Outlook、PowerPoint、Project、Visio 或 Word。|  
|**loadBehavior**|可选。 默认情况下， **loadBehavior**通过将该值设置为。 为进行调试，可以通过将此值设置为 2 来禁用 VSTO 外接程序。 有关详细信息，请参阅标题为 LoadBehavior 值中的表[VSTO 外接程序的注册表项](../vsto/registry-entries-for-vsto-add-ins.md)。|  
|**KeyName**|必须的。 此值是该应用程序将用于加载 VSTO 外接程序的注册表项名称。 有关详细信息，请参阅[VSTO 外接程序的注册表项](../vsto/registry-entries-for-vsto-add-ins.md)。|  
  
 **AppAddin**元素具有以下子元素。  
  
### <a name="friendlyname"></a>FriendlyName  
 可选。 **FriendlyName**元素述[ &#60;friendlyName&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md)。  
  
### <a name="description"></a>说明  
 可选。 **说明**元素述[&#60;说明&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/description-element-office-development-in-visual-studio.md)。  
  
### <a name="formregions"></a>formRegions  
 仅为包含窗体区域的 Outlook VSTO 外接程序所需。 **FormRegions**元素述[ &#60;formRegions&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/formregions-element-office-development-in-visual-studio.md)。  
  
## <a name="vsto-add-in-example"></a>VSTO 外接程序示例  
  
### <a name="description"></a>描述  
 下面的代码示例阐释了**appAddin**部署使用的 Outlook 解决方案中的元素[!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]。 此代码示例摘自[Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)。  
  
### <a name="code"></a>代码  
  
```xml  
<vstov4:appAddIn   
  application="Outlook"   
  loadBehavior="3"   
  keyName="ContosoOutlookAddIn">  
  <vstov4:friendlyName>  
    ContosoOutlookAddIn  
  </vstov4:friendlyName>  
  <vstov4:description>  
    ContosoOutlookAddIn - Outlook VSTO Add-in   
    created with Visual Studio Tools for Office  
  </vstov4:description>  
  <vstov4:formRegions>  
    <vstov4:formRegion  
        name="OutlookAddIn1.FormRegion1">  
      <vstov4:messageClass name="IPM.Note" />  
      <vstov4:messageClass name="IPM.Contact" />  
      <vstov4:messageClass name="IPM.Appointment" />  
    </vstov4:formRegion>  
  </vstov4:formRegions>  
</vstov4:appAddIn>  
```  
  
## <a name="see-also"></a>请参阅  
 [Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)   
 [部署 Office 解决方案的清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  