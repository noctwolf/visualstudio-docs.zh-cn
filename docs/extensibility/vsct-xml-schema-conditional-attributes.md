---
title: VSCT XML 架构条件属性 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, conditional attributes
- conditional attributes (VSCT XML schema)
ms.assetid: 754d4f32-319b-44c9-915f-f7c60e53222e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 95308f286506aa9e032e3923bbff23c90d464d48
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55070664"
---
# <a name="vsct-xml-schema-conditional-attributes"></a>VSCT XML 架构条件属性
您可以将条件特性应用于所有列表和项。 逻辑运算符和符号扩展表达式的计算结果为 true 或 false。 如果为 true，生成的输出中包含关联的列表或项。  
  
 你可以测试针对其他标记扩展或常量的标记扩展。 该函数`Defined()`测试是否定义了特定名称，即使它没有任何价值。  
  
 当条件特性应用于列表中时，条件被应用于列表中每个子元素。 如果子元素本身包含条件属性，然后其条件与父级表达式通过结合 AND 运算。  
  
 值 1、 '1' 和 'true' 的计算结果为 true，和 0、"0"和 false 计算结果为 false。  
  
## <a name="operators"></a>运算符  
 使用以下运算符来评估条件表达式。  
  
|运算符|定义|  
|--------------|----------------|  
|(,)|分组|  
|!|逻辑“非”|  
|\<, >, \<=, >=, ==, !=|关系式与等式|  
|和|Boolean|  
|或|Boolean|  
  
## <a name="examples"></a>示例  
  
```xml  
<Menu Condition="Defined(DEBUG)" ...  
</Menu>  
  
<Menu Condition="%(SKU_MODE) = 'Demo'" ...  
</Menu>  
  
<Menus Condition="Defined(DEBUG)">  
    <Menu ...  
    </Menu>  
</Menus>  
  
<Menus Condition="Defined(DEMO_SKU)">  
    <Menus Condition="!Defined(DEBUG)">  
        <Menu ...  
        </Menu>  
    </Menus>  
  
    <Menu ...  
    </Menu>  
</Menus>  
  
<Menus Condition="(Defined(DEMO_SKU) or Defined(SAMPLE_SKU))   
and !Defined(DEBUG)">  
    <Menu ...  
    </Menu>  
</Menus>  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令表 (。Vsct) 文件](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)