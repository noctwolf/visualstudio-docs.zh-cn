---
title: Extern 元素 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Extern
helpviewer_keywords:
- VSCT XML schema elements, Extern
- Extern element (VSCT XML schema)
ms.assetid: db6c3ddd-a1ba-450a-897a-bb568a5377fc
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cc1b406fa0675a481b538446f9c4bf0716475872
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49171870"
---
# <a name="extern-element"></a>Extern 元素
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Extern 元素引用任何要在编译时合并使用.vsct 文件的外部标头 (.h) 文件。 要合并的文件必须位于包含路径提供给 VSCT 编译器或引用的[包括元素](../extensibility/include-element.md)。 这些文件可能是其他.vsct 文件或 c + + 标头文件。  
  
 标头文件中的定义必须是窗体的"#define [符号] [值]"的值可能是另一个符号，如果以前已定义。 定义可用于条件语句的命令项。 实际上未使用任何符号将被放弃。  
  
 CommandTable 元素  
Extern 元素  
  
## <a name="syntax"></a>语法  
  
```  
<Extern href="stdidcmd.h" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|href|必须的。 标头文件的路径：<br /><br /> href="stdidcmd.h"|  
|条件|可选。 请参阅[条件属性](../extensibility/vsct-xml-schema-conditional-attributes.md)。|  
|语言|可选。 默认语言的所有[\<字符串 >](../extensibility/strings-element.md)命令表中的元素：<br /><br /> 语言 ="en-我们"|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|无。|无。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[CommandTable 元素](../extensibility/commandtable-element.md)|定义表示命令的元素的所有 — 也就是说，菜单项、 菜单、 工具栏和组合框 — VSPackage 提供到 IDE。|  
  
## <a name="example"></a>示例  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-  
  18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <Extern href="C:\VSCore\vscommon\inc\vsshlids.h"/>  
    …  
  <Commands package="guidMyPackage">  
</CommandTable>  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令表 (。Vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Vspackage 如何添加用户界面元素](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [命令、菜单和工具栏](../extensibility/internals/commands-menus-and-toolbars.md)

