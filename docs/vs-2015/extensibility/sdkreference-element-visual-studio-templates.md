---
title: SDKReference 元素 （Visual Studio 模板） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72c8b352-0b7a-42b3-ba5d-2a2d1e90c34b
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0f9b9469079e8832f424e43bf643d866981c652b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469819"
---
# <a name="sdkreference-element-visual-studio-templates"></a>SDKReference 元素（Visual Studio 模板）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[SDKReference 元素 （Visual Studio 模板）](https://docs.microsoft.com/visualstudio/extensibility/sdkreference-element-visual-studio-templates)。  
  
指定项模板使用 SDK 引用。  
  
## <a name="syntax"></a>语法  
  
```xml  
<VSTemplate>      
    <TemplateContent>          
        <References>              
            <Reference>  
                <SDKReference>SDKname</SDKReference>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[引用](../extensibility/reference-element-visual-studio-templates.md)|指定向项目添加项时要添加的程序集引用。|  
  
## <a name="text-value"></a>文本值  
 需要一个文本值。  
  
## <a name="remarks"></a>备注  
 本文本指定实例化项模板时要向项目添加的 SDK 引用。  
  
```xml  
<VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">   
    <TemplateData> . . . </TemplateData>   
    <TemplateContent>   
        <References>   
            <Reference>   
                <SDKReference>Microsoft Visual C++ Runtime Package, Version=11.0.0.0</SDKReference>  
...  
```  
  
## <a name="see-also"></a>请参阅  
 [References 元素 （Visual Studio 模板）](../extensibility/references-element-visual-studio-templates.md)   
 [Reference 元素 （Visual Studio 模板）](../extensibility/reference-element-visual-studio-templates.md)   
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)

