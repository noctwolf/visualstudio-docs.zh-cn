---
title: '&lt;更新&gt;元素 （Visual Studio 中的 Office 开发） |Microsoft 文档'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- update element
- <update> element
- application manifests [Office development in Visual Studio], <update> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2f0e1fdc26e285ce9b6a1fd5ecc1aa638fe909b8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ltupdategt-element-office-development-in-visual-studio"></a>&lt;更新&gt;元素 （Visual Studio 中的 Office 开发）
  `update`元素指定的更新的解决方案将检查的间隔。  
  
## <a name="syntax"></a>语法  
  
```  
<update  
  enabled>  
  <expiration  
    maximumAge  
    unit  
  />  
</update>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `update` 元素是必需的，它位于 `vstav3` 命名空间中。  
  
 `update`元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必须的。 将 enabled 设置为下列值之一：<br /><br /> -   **true**检查更新。<br />-   **false**以防止检查更新。|  
  
 `update`元素具有以下子元素。  
  
### <a name="expiration"></a>过期  
 `expiration` 元素是必需的，它位于 `vstav3` 命名空间中。 此元素指定的更新的解决方案检查的间隔。  
  
 `expiration`元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`maximumAge`|必需。 这将设置为一个整数。|  
|`unit`|必须的。 设置`unit`为以下值之一：<br /><br /> -   **小时数**<br />-   **天**<br />-   **周**|  
  
## <a name="example-of-always-checking-for-updates"></a>始终检查更新的示例  
  
### <a name="description"></a>描述  
 下面的代码示例阐释了`update`设置为始终检查更新 Office 解决方案中的元素。  
  
### <a name="code"></a>代码  
  
```  
<vstav3:update enabled="true" />  
```  
  
## <a name="example-of-setting-a-default-update-interval"></a>设置默认更新间隔的示例  
  
### <a name="description"></a>描述  
 下面的代码示例阐释了`update`Office 解决方案的应用程序清单中的元素。 此代码示例摘自 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中提供的一个更大的示例。  
  
### <a name="code"></a>代码  
  
```  
<vstav3:update enabled="true">  
    <vstav3:expiration maximumAge="7" unit="days" />  
</vstav3:update>  
```  
  
## <a name="see-also"></a>请参阅  
 [通过使用 ClickOnce 部署 Office 解决方案](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  