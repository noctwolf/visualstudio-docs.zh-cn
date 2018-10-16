---
title: 内部函数 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- _String_length_
- _Param_
- _Curr_
- _Old_
- _Nullterm_length_
- _Inexpressible_
ms.assetid: adf29f8c-89fd-4a5e-9804-35ac83e1c457
caps.latest.revision: 9
author: corob-msft
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1b50742c0176b8c880d3ed0b58b7b8ef76355777
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49174481"
---
# <a name="intrinsic-functions"></a>内部函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在 SAL 表达式可以是 C/c + + 表达式，前提是不具有副作用的表达式，例如，+ +、--，和所有在此上下文中具有副作用的函数调用。  但是，SAL 提供一些类似函数的对象以及可以在 SAL 表达式中使用一些保留的符号。 这些称为*内部函数*。  
  
## <a name="general-purpose"></a>通用  
 以下内部函数批注的 sal 提供常规实用程序。  
  
|批注|描述|  
|----------------|-----------------|  
|`_Curr_`|同义词所批注的对象。  当`_At_`正在使用中，批注`_Curr_`的第一个参数相同`_At_`。  否则，将参数或批注与从词法上关联的整个函数/返回值。|  
|`_Inexpressible_(expr)`|表示一个缓冲区的大小是太复杂，无法通过使用批注表达式表示的情况 — 例如，通过扫描输入的数据集，然后再计算的计算时所选成员。|  
|`_Nullterm_length_(param)`|`param` 是最多缓冲区，但不是包括 null 终止符中的元素数。 它可应用于非聚合，非 void 类型的任何缓冲。|  
|`_Old_(expr)`|在不满足前提条件，计算时`_Old_`将返回输入的值`expr`。  当它计算后置条件中时，它将返回值`expr`根据它进行计算中不满足前提条件。|  
|`_Param_(n)`|`n`个参数的函数，从 1 到计数`n`，和`n`是文本的整数常量。 如果名为的参数，此批注等同于按名称访问该参数。 **注意：** `n`可能指由省略号，或者可能在不使用名称函数原型中使用的位置参数。|  
|`return`|C/c + + 保留关键字`return`可以 SAL 表达式中使用以指示函数的返回值。  在 post 状态; 值才可用它会导致语法错误之前状态使用它。|  
  
## <a name="string-specific"></a>特定于字符串  
 下面的内部函数批注启用操作的字符串。 这些函数的所有四个具有相同的用途： 若要返回的 null 终止符之前找到的类型的元素数。 差异几种类型的引用的元素中的数据。 请注意，如果你想要指定以 null 结尾的长度的缓冲区，不由字符，请使用`_Nullterm_length_(param)`批注与上一节。  
  
|批注|描述|  
|----------------|-----------------|  
|`_String_length_(param)`|`param` 是为字符串，但不是包括 null 终止符中的元素数。 此批注被保留的字符串的字符类型。|  
|`strlen(param)`|`param` 是为字符串，但不是包括 null 终止符中的元素数。 此批注保留以供使用的字符数组和类似于 C 运行时函数[strlen （)](http://msdn.microsoft.com/library/16462f2a-1e0f-4eb3-be55-bf1c83f374c2)。|  
|`wcslen(param)`|`param` 是 （但不是包括） 在字符串中的元素数目 null 终止符。 此批注保留以供使用宽字符数组和类似于 C 运行时函数[wcslen （)](http://msdn.microsoft.com/library/16462f2a-1e0f-4eb3-be55-bf1c83f374c2)。|  
  
## <a name="see-also"></a>请参阅  
 [使用 SAL 注释减少 C/c + + 代码缺陷](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [了解 SAL](../code-quality/understanding-sal.md)   
 [对函数参数和返回值进行批注](../code-quality/annotating-function-parameters-and-return-values.md)   
 [对函数行为进行批注](../code-quality/annotating-function-behavior.md)   
 [批注结构和类](../code-quality/annotating-structs-and-classes.md)   
 [对锁定行为进行批注](../code-quality/annotating-locking-behavior.md)   
 [指定何时以及在何处应用批注](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [最佳做法和示例](../code-quality/best-practices-and-examples-sal.md)



