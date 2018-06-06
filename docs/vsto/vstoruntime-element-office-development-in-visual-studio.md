---
title: '&lt;vstoRuntime&gt;元素 （Visual Studio 中的 Office 开发）'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <vstoRuntime> element
- <vstoRuntime> element
- vstoRuntime element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d21e097c0a05dfba2aa15bc41e37441ae02a63e4
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34768061"
---
# <a name="ltvstoruntimegt-element-office-development-in-visual-studio"></a>&lt;vstoRuntime&gt;元素 （Visual Studio 中的 Office 开发）
  `vstoRuntime` 命名空间的 `vstav3` 元素包含针对特定 Office 解决方案的受支持的 Visual Studio Tools for Office Runtime 版本。  
  
## <a name="syntax"></a>语法  
  
```xml  
<vstoRuntime  
    release  
    version  
    supportUrl />  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `vstoRuntime` 元素是必需的，它位于 `vstav3` 命名空间中。 如果 Office 解决方案支持两个版本的 Visual Studio Tools for Office Runtime，则应用程序清单中存在两个 `vstoRuntime` 元素。  
  
 `vstoRuntime` 元素具有以下属性。  
  
|特性|描述|  
|---------------|-----------------|  
|`release`|必须的。 Visual Studio Tools for Office Runtime 的发布版本。|  
|`version`|必须的。 Visual Studio Tools for Office Runtime 的版本号。|  
|`supportUrl`|可选。 指向 Visual Studio Tools for Office Runtime 安装位置的链接。|  
  
 `vstoRuntime` 不包含任何元素。  
  
## <a name="example"></a>示例  
 下面的代码示例演示 Office 解决方案的应用程序清单中的 `vstoRuntime` 元素，该解决方案是使用 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]部署的。 此代码示例摘自[Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)。  
  
```xml  
<vstav3:vstoRuntime  
    release="VSTOR40Beta1"  
    version="10.0.20303"  
    supportUrl="http://www.microsoft.com" />  
```  
  
## <a name="see-also"></a>请参阅  
 [Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)   
 [部署 Office 解决方案的清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  