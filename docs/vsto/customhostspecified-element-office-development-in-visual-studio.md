---
title: "&lt;f i e d&gt;元素 （Visual Studio 中的 Office 开发） |Microsoft 文档"
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
- application manifests [Office development in Visual Studio], <customHostSpecified> element
- <customHostSpecified> element
- customHostSpecified element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 80007310f5556bcc8c67b61e7ff41953cc7c900e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="ltcustomhostspecifiedgt-element-office-development-in-visual-studio"></a>&lt;f i e d&gt;元素 （Visual Studio 中的 Office 开发）
  `customHostSpecified`元素指示此解决方案不是独立的应用程序。 Office 解决方案包含承载于 Microsoft Office 应用程序内的组件。  
  
## <a name="syntax"></a>语法  
  
```  
<customHostSpecified />  
```  
  
## <a name="elements-and-attributes"></a>元素和属性  
 `customHostSpecified`元素是必需的 Office 解决方案。 此元素处于`co.v1`命名空间和指定此部署包含将在自定义主机，内部部署的组件，并且不是独立的应用程序。  
  
 此元素是第一个子`<entrypoint>`应用程序清单中的元素。 可以有中，没有其他子元素`<entrypoint>`元素或[!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]将在安装过程中引发验证错误。  
  
 此元素具有任何属性，也没有子元素。  
  
## <a name="example"></a>示例  
 下面的代码示例阐释了`customHostSpecified`Office 解决方案的应用程序清单中的元素。 此代码示例摘自 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)中提供的一个更大的示例。  
  
```  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>  
```  
  
## <a name="see-also"></a>请参阅  
 [Application Manifests for Office Solutions](../vsto/application-manifests-for-office-solutions.md)   
 [Office 解决方案的部署清单](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce 应用程序清单](/visualstudio/deployment/clickonce-application-manifest)  
  
  