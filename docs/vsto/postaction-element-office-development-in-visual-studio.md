---
title: '&lt;o n&gt;元素 （Visual Studio 中的 Office 开发）'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <postAction> element
- <postAction> element
- postAction element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: dcab31eea406da695bdedd21b21c0d86cacea220
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2018
ms.locfileid: "34693112"
---
# <a name="ltpostactiongt-element-office-development-in-visual-studio"></a>&lt;o n&gt;元素 （Visual Studio 中的 Office 开发）
  `postAction` 命名空间的 `vstav3` 元素包含与部署后操作（在安装 Office 解决方案后运行）相关联的 `entrypoint` 元素和所有 `postActionData` 元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
<postAction>  
  <entryPoint>  
  </entryPoint>  
  <postActionData>  
  </postActionData>  
</postAction>  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `postAction` 元素是可选的，它位于 `vstav3` 命名空间中。 每个部署后操作的应用程序清单中只定义了一个 `postAction` 元素。  
  
 `postAction` 元素没有属性。  
  
 `postAction` 具有下列元素。  
  
### <a name="entrypoint"></a>entrypoint  
 可选。 角色`entryPoint`中的元素`vstav3`中定义命名空间[&#60;入口点&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)。  
  
### <a name="postactiondata"></a>postActionData  
 可选。 角色`postActionData`中的元素`vstav3`中定义命名空间[ &#60;a t a&#62;元素&#40;Visual Studio 中的 Office 开发&#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md)。  
  
## <a name="post-deployment-action-example"></a>部署后操作示例  
  
### <a name="description"></a>描述  
 下面的代码示例演示 Office 解决方案的应用程序清单中的 `postAction` 元素，该解决方案是使用 [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]部署的。 此代码示例摘自[Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)。  
  
### <a name="code"></a>代码  
  
```xml
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
```  
  
## <a name="see-also"></a>请参阅  
 [Office 解决方案的应用程序清单](../vsto/application-manifests-for-office-solutions.md)   
 [部署 Office 解决方案的清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  