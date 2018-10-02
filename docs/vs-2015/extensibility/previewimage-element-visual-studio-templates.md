---
title: PreviewImage 元素 （Visual Studio 模板） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- <PreviewImage> Element (Visual Studio Templates)
- PreviewImage Element (Visual Studio Templates)
ms.assetid: d1796f20-523b-4e0d-8ac3-ca87f3b5a9b6
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 916b500862f614a58c4c7234a42fef299e8e206d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482760"
---
# <a name="previewimage-element-visual-studio-templates"></a>PreviewImage 元素（Visual Studio 模板）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[PreviewImage 元素 （Visual Studio 模板）](https://docs.microsoft.com/visualstudio/extensibility/previewimage-element-visual-studio-templates)。  
  
指定的预览图像，为的文件名称，将出现在任何一个的预览图像**新的项目**或**添加新项**对话框。  
  
 \<VSTemplate >  
 \<TemplateData >  
 \<PreviewImage >  
  
## <a name="syntax"></a>语法  
  
```  
<PreviewImage>"filename"</PreviewImage>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|必需的元素。<br /><br /> 此模板分类并定义如何显示在**新的项目**或**添加新项**对话框。|  
  
## <a name="text-value"></a>文本值  
 需要一个文本值。  
  
 文本必须是一个字符串，表示文件名称。  
  
## <a name="remarks"></a>备注  
 `PreviewImage` 是可选元素。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 模板架构参考](../extensibility/visual-studio-template-schema-reference.md)   
 [创建项目和项模板](../ide/creating-project-and-item-templates.md)

