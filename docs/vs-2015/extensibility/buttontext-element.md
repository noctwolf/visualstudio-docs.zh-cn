---
title: ButtonText 元素 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d7cbf92a762fd3fce80e7f59e77c03c8cd81cc22
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469651"
---
# <a name="buttontext-element"></a>ButtonText 元素
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[ButtonText 元素](https://docs.microsoft.com/visualstudio/extensibility/buttontext-element)。  
  
此字段允许您指定各种菜单中显示的文本。 默认情况下，`ButtonText`元素出现在菜单控制器。 `ButtonText`元素也将成为默认如果其他文本字段为空白。 `ButtonText`元素不能为空，即使指定的其他文本字段。  
  
## <a name="syntax"></a>语法  
  
```  
<ButtonText>My Command</ButtonText>  
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
|[Strings 元素](../extensibility/strings-element.md)|文本元素，如分组`ButtonText`和`CommandName`。|  
  
## <a name="text-value"></a>文本值  
 文本值`ButtonText`元素提供的菜单项、 combos 和其他用户界面 (UI) 元素包含可见文本显示的文本。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令表格 (.Vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

