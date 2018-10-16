---
title: IDSymbol 元素 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDSymbol element (VSCT XML schema)
- VSCT XML schema elements, IDSymbol
ms.assetid: 760cfd20-3c06-422c-9103-98bfa1f387f8
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3b4876144093d5e937a194095af1b128dc3efabd
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49253040"
---
# <a name="idsymbol-element"></a>IDSymbol 元素
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`IDSymbol`元素包含表示菜单、 组或命令的 guid: id 对中的 ID。 GUID 来自父`GuidSymbol`元素。 `IDSymbol`元素具有`name`提供的 ID，它包含在一个友好名称的属性`value`属性。  
  
## <a name="syntax"></a>语法  
  
```  
<IDSymbol name=ElementName value="0x0010" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|必须的。 ID 符号名称。|  
|值|必须的。 ID 符号的数字 ID 值。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[GuidSymbol 元素](../extensibility/guidsymbol-element.md)|包含表示菜单、 组或命令的 guid: id 对中的 GUID。 对 `IDSymbol` 元素进行分组。|  
  
## <a name="remarks"></a>备注  
 每个`IDSymbol`元素中的给定`GuidSymbol`元素必须具有一个唯一`value`。 但是， `IDSymbol` ，只要它们具有不同的父，可以在包中存在具有相同的值的元素。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令表格 (.Vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

