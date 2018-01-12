---
title: "&lt;postActions&gt;元素 （Visual Studio 中的 Office 开发） |Microsoft 文档"
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
- application manifests [Office development in Visual Studio], <postActions> element
- postActions element
- <postActions> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: bbe0708ce97eb6410f006b6dcdc8d8194907b9c1
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="ltpostactionsgt-element-office-development-in-visual-studio"></a>&lt;postActions&gt;元素 （Visual Studio 中的 Office 开发）
  `postActions` 命名空间的 `vstav3` 元素包含描述部署后操作（在安装 Office 解决方案后运行）的 `postAction` 所有元素。  
  
## <a name="syntax"></a>语法  
  
```  
<postActions>  
  <postAction>  
    <entryPoint>  
    </entryPoint>  
    <postActionData>  
    </postActionData>  
  </postAction>  
</postActions>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `postActions` 元素是可选的，它位于 `vstav3` 命名空间中。 在应用程序清单中定义的 `postActions` 元素只有一个。  
  
 `postActions` 元素没有属性。  
  
 `postActions` 具有以下元素。  
  
### <a name="postaction"></a>postAction  
 可选。 角色`postAction`中的元素`vstav3`中定义命名空间[&#60; o n &#62;元素 &#40; Visual Studio &#41; 中的 Office 开发](../vsto/postaction-element-office-development-in-visual-studio.md).  
  
## <a name="post-deployment-action-example"></a>部署后操作示例  
  
### <a name="description"></a>描述  
 下面的代码示例演示 Office 解决方案的应用程序清单中的 `postActions` 元素，该解决方案是使用 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]部署的。 此代码示例摘自 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中提供的一个更大的示例。  
  
### <a name="code"></a>代码  
  
```  
<vstav3:postActions>  
  <vstav3:postAction>  
    <vstav3:entryPoint   
      class="PostDeploymentAction.PostDeploymentActionSample">  
      <assemblyIdentity   
        name="PostDeploymentAction"   
        version="1.0.0.0"   
        language="neutral"   
        processorArchitecture="msil" />  
    </vstav3:entryPoint>  
    <vstav3:postActionData>  
    </vstav3:postActionData>  
  </vstav3:postAction>  
</vstav3:postActions>  
```  
  
## <a name="see-also"></a>请参阅  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  