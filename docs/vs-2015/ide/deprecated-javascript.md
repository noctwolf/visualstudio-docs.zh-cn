---
title: '&lt;不推荐使用&gt;(JavaScript) |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf33d371-59da-4310-95ee-d7524fd9d58c
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 220f320eba6231161328a08914848114db7ae02b
ms.sourcegitcommit: 71218ffc33da325cc1b886f69ff2ca50d44f5f33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "48880456"
---
# <a name="ltdeprecatedgt-javascript"></a>&lt;不推荐使用&gt;(JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[Visual Studio 2017 文档](/visualstudio/)。  
  
指定一个不推荐使用的函数或方法。  
  
## <a name="syntax"></a>语法  
  
```  
<deprecated  
    type="deprecate|remove"  
    locid="descriptionID">description  
</deprecated>  
```  
  
#### <a name="parameters"></a>参数  
 `type`  
 可选。 指定是否函数或方法中将删除未来版本中，或是否函数或方法已被移除，并且它的使用可能会导致错误。 设置为`deprecate`来指定，将在未来的版本中删除的函数或方法。 设置为`remove`指定的函数或方法已被移除。  
  
 `locid`  
 可选。 有关函数或方法的本地化信息标识符。 该标识符是任一成员 ID 或其对应于`name`属性在 OpenAjax 元数据定义消息绑定中的值。 标识符类型取决于中指定的格式[ \<loc >](../ide/loc-javascript.md)元素。  
  
 `description`  
 可选。 函数或不推荐使用的方法的说明。  
  
## <a name="remarks"></a>备注  
 用于批注函数，它包含的元素`<deprecated>`，必须放置在任何语句之前在函数体。 将函数标记为已弃用后，我们建议你将为其[\<摘要 >](../ide/summary-javascript.md)具有元素`<deprecated>`元素。  
  
## <a name="example"></a>示例  
 下面的代码演示如何使用`<deprecated>`元素。  
  
```javascript  
function areaFunction(radiusParam) {  
    /// <deprecated type="deprecate" >Determines the area of a circle when supplied a radius parameter.</deprecated>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>请参阅  
 [XML 文档注释](../ide/xml-documentation-comments-javascript.md)



