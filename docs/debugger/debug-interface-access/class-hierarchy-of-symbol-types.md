---
title: 类符号类型的层次结构 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- symbols [DIA SDK], class hierarchies
ms.assetid: 0ccd6990-4654-44cd-a6f3-bdd82fe90f6c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66bada6b1c1f0a925277fcc1716659ba431c35d8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55039953"
---
# <a name="class-hierarchy-of-symbol-types"></a>符号类型的类层次结构
下表介绍的类层次结构中的符号类型。  
  
## <a name="symbol-types"></a>符号类型  
  
|符号类型|说明|  
|-----------------|-----------------|  
|[UDT](../../debugger/debug-interface-access/udt.md)|符号用于表示每个类、 结构和联合。|  
|[枚举（调试接口访问 SDK）](../../debugger/debug-interface-access/enum-debug-interface-access-sdk.md)|枚举类型的符号。|  
|[PointerType](../../debugger/debug-interface-access/pointertype.md)|指针类型的符号。|  
|[ArrayType](../../debugger/debug-interface-access/arraytype.md)|数组类型的符号。|  
|[BaseType](../../debugger/debug-interface-access/basetype.md)|对基类型的符号|  
|[Typedef（调试接口访问 SDK）](../../debugger/debug-interface-access/typedef-debug-interface-access-sdk.md)|引入了其他类型的名称的符号。|  
|[BaseClass](../../debugger/debug-interface-access/baseclass.md)|用于用户定义类型 (UDT) 的每个基类的符号。|  
|[友元（调试接口访问 SDK）](../../debugger/debug-interface-access/friend-debug-interface-access-sdk.md)|友元类和友元函数的符号。|  
|[FunctionType](../../debugger/debug-interface-access/functiontype.md)|对于每个唯一函数签名的符号。|  
|[FunctionArgType](../../debugger/debug-interface-access/functionargtype.md)|每个参数的函数的的符号。|  
|[VTableShape](../../debugger/debug-interface-access/vtableshape.md)|虚拟表的大小的符号。|  
|[VTable](../../debugger/debug-interface-access/vtable.md)|一个虚拟表的符号。|  
|[CustomType](../../debugger/debug-interface-access/customtype.md)|对于供应商定义的类型的符号。|  
|[ManagedType](../../debugger/debug-interface-access/managedtype.md)|对于元数据中定义的类型的符号。|  
|[维度](../../debugger/debug-interface-access/dimension.md)|数组维数的符号。|  
  
> [!NOTE]
>  每个符号可以保存有关符号，以及对其他符号的引用信息的属性。 单个符号主题中列出了这些属性。  
  
## <a name="see-also"></a>请参阅  
 [CV_access_e 枚举](../../debugger/debug-interface-access/cv-access-e.md)   
 [符号类型的词法层次结构](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [符号和符号标记](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)