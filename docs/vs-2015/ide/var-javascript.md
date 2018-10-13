---
title: '&lt;var&gt; (JavaScript) |Microsoft Docs'
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
- <var> JavaScript XML tag
- var JavaScript XML tag
ms.assetid: 34ff9023-c81c-46d1-85b6-0022f0962e66
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a1a8f46f6d5cef0d786110fb27d6ff4c1adce26b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49223703"
---
# <a name="ltvargt-javascript"></a>&lt;var&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

指定变量的文档信息。  
  
## <a name="syntax"></a>语法  
  
```  
<var type="ValueType" integer="true|false"  
    domElement="true|false" mayBeNull="true|false"  
    elementType="ArrayElementType" elementInteger="true|false"  
    elementDomElement="true|false" elementMayBeNull="true|false"  
    helpKeyword="keyword" locid="descriptionID">description  
</var>   
```  
  
#### <a name="parameters"></a>参数  
 `type`  
 可选。 变量的数据类型。 类型可以是以下值之一：  
  
-   是在 ECMAScript 5 规范中，例如 ECMAScript 语言类型`Number`和`Object`。  
  
-   DOM 对象，例如`HTMLElement`， `Window`，和`Document`。  
  
-   JavaScript 构造函数。  
  
 `integer`  
 可选。 如果`type`是`Number`，指定该变量是否是一个整数。 设置为`true`以指示该变量是一个整数; 否则，将设置为`false`。 Visual Studio 不使用此属性以提供 IntelliSense 信息。  
  
 `domElement`  
 可选。 此属性已弃用;`type`特性将优先于此属性。 此属性指定是否有案可稽的变量是一个 DOM 元素。 设置为`true`以指定该变量是一个 DOM 元素; 否则，将设置为`false`。 如果`type`未设置属性和`domElement`设置为`true`，IntelliSense 将有案可稽的变量视为`HTMLElement`执行语句完成时。  
  
 `mayBeNull`  
 可选。 指定是否可以设置有案可稽的变量为 null。 设置为`true`若要指示为 null; 否则为，可以设置的变量，将设置为`false`。 默认值为 `false`。 Visual Studio 不使用此属性以提供 IntelliSense 信息。  
  
 `elementType`  
 可选。 如果`type`是`Array`，此属性指定数组中元素的类型。  
  
 `elementInteger`  
 可选。 如果`type`是`Array`并`elementType`是`Number`，此属性指定数组中的元素是否为整数。 设置为`true`来指示数组中的元素都是整数; 否则，将设置为`false`。 Visual Studio 不使用此属性以提供 IntelliSense 信息。  
  
 `elementDomElement`  
 可选。 此属性已弃用;`elementType`特性将优先于此属性。 如果`type`是`Array`，此属性指定数组中的元素是否 DOM 元素。 设置为`true`来指定元素的 DOM 元素; 否则，将设置为`false`。 如果`elementType`未设置属性和`elementDomElement`设置为`true`，IntelliSense 将作为数组中的每个元素`HTMLElement`执行语句完成时。  
  
 `elementMayBeNull`  
 可选。 如果`type`是`Array`，指定是否可以设置数组中的元素为 null。 设置为`true`若要指示为 null; 否则为，可以设置数组中的元素，将设置为`false`。 默认值为 `false`。 Visual Studio 不使用此属性以提供 IntelliSense 信息。  
  
 `helpKeyword`  
 可选。 F1 帮助关键字。  
  
 `locid`  
 可选。 有关变量的本地化信息的标识符。 该标识符是任一成员 ID 或其对应于`name`属性在 OpenAjax 元数据定义消息绑定中的值。 标识符类型取决于中指定的格式[ \<loc >](../ide/loc-javascript.md)标记。  
  
 `description`  
 可选。 变量的说明。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何使用`<var>`元素。  
  
```javascript  
/// <var>A rectangle that has a width of 5.</var>  
var Rectangle = {  
    /// <field type = 'Number'>The width of the rectangle.</field>  
    wid: 5,  
    /// <field type = 'Number'>The length of the rectangle.</field>  
    len: 0,  
    /// <field type='Number'>Returns the area of the rectangle.</field>  
    getArea: function (wid, len) {  
        return len * wid;  
    }  
}  
```  
  
## <a name="see-also"></a>请参阅  
 [XML 文档注释](../ide/xml-documentation-comments-javascript.md)



