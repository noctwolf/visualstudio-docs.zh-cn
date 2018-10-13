---
title: '&lt;摘要&gt;(JavaScript) |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- summary JavaScript XML tag
- <summary> JavaScript XML tag
ms.assetid: 6540582d-bdb3-42ec-ad2f-c176783e6f9c
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8ee08ed1e2a5feb1f5a87f7d6337a4b5f1e47a22
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49252403"
---
# <a name="ltsummarygt-javascript"></a>&lt;摘要&gt;(JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

指定函数或方法的说明。  
  
## <a name="syntax"></a>语法  
  
```  
<summary locid="descriptionID">description  
</summary>  
```  
  
#### <a name="parameters"></a>参数  
 `locid`  
 可选。 有关函数或方法的本地化信息标识符。 该标识符是任一成员 ID 或其对应于`name`属性在 OpenAjax 元数据定义消息绑定中的值。 标识符类型取决于中指定的格式[ \<loc >](../ide/loc-javascript.md)元素。  
  
 `description`  
 可选。 函数或方法的说明。  
  
## <a name="remarks"></a>备注  
 用于批注函数，它包含的元素[\<摘要 >](../ide/summary-javascript.md)， [ \<param >](../ide/param-javascript.md)，以及[\<返回 >](../ide/returns-javascript.md)，必须在任何语句之前在函数体中放置。  
  
## <a name="example"></a>示例  
 下面的代码演示如何使用`<summary>`元素。  
  
```javascript  
function areaFunction(radiusParam)  
{  
    /// <summary>Determines the area of a circle when supplied a radius parameter.</summary>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>请参阅  
 [XML 文档注释](../ide/xml-documentation-comments-javascript.md)



