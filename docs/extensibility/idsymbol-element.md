---
title: IDSymbol 元素 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDSymbol element (VSCT XML schema)
- VSCT XML schema elements, IDSymbol
ms.assetid: 760cfd20-3c06-422c-9103-98bfa1f387f8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 71979bd4f859257555c9d72ac5521a5ae21b9ed4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127521"
---
# <a name="idsymbol-element"></a>IDSymbol 元素
`IDSymbol`元素包含的 guid: id 对，表示菜单、 组或命令的 ID。 GUID 来自父`GuidSymbol`元素。 `IDSymbol`元素具有`name`提供的 ID 中包含的友好名称的属性`value`属性。  
  
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
|[GuidSymbol 元素](../extensibility/guidsymbol-element.md)|包含表示菜单、 组或命令的 guid: id 对的 GUID。 对 `IDSymbol` 元素进行分组。|  
  
## <a name="remarks"></a>备注  
 每个`IDSymbol`元素中的给定`GuidSymbol`元素必须具有唯一`value`。 但是， `IDSymbol` ，只要它们具有不同的父，可以在包中存在具有相同的值的元素。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Studio 命令表格 (.Vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)