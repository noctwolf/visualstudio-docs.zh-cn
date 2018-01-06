---
title: "ButtonText 元素 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c9f2374af403c37f18d1aa91700e51bd038a71c6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="buttontext-element"></a>ButtonText 元素
此字段允许你指定各种菜单中显示的文本。 默认情况下，`ButtonText`元素出现在菜单控制器中。 `ButtonText`元素也成为默认的如果其他文本字段为空白。 `ButtonText`元素不能为空，即使指定了其他文本字段。  
  
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
 文本值`ButtonText`元素提供的菜单项、 组合和其他用户界面 (UI) 元素具有可见文本显示的文本。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令表格 (.Vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)