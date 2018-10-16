---
title: TargetPlatformName 元素 （Visual Studio 模板） |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a6b1f45-b5d6-418e-add1-87ee8f15033d
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dea9ff1c1c27c88592a4a13c55ae06b07328d811
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49211713"
---
# <a name="targetplatformname-element-visual-studio-templates"></a>TargetPlatformName 元素（Visual Studio 模板）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

指定项目模板面向的平台。 此元素用于指定项目模板用于创建 [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] 应用。  
  
## <a name="syntax"></a>语法  
  
```xml  
<VSTemplate>  
    <TemplateData>   
        <TargetPlatformName> OperatingSystem</TargetPlatformName>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[RequiredPlatformVersion](../extensibility/requiredplatformversion-element-visual-studio-templates.md)|指定项目模板面向的操作系统版本。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|将此模板分类并定义此模板在 **“新建项目”** 或 **“添加新项”** 对话框中的显示方式。|  
  
## <a name="text-value"></a>文本值  
 需要一个文本值。  
  
## <a name="remarks"></a>备注  
 文本必须为 **Windows**。  
  
## <a name="example"></a>示例  
 此示例指定项目模板面向 [!INCLUDE[win8](../includes/win8-md.md)] 或更高版本。  
  
```xml  
<VSTemplate Type="Project" Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">   
    <TemplateData>   
        <TargetPlatformName>Windows</TargetPlatformName>   
        <RequiredPlatformVersion>8</RequiredPlatformVersion>   
    </TemplateData>   
    <TemplateContent> </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>请参阅  
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)

