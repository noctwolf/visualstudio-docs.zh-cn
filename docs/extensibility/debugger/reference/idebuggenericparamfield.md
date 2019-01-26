---
title: IDebugGenericParamField | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugGenericParamField interface
ms.assetid: ba24f499-5ba7-4c67-83e6-923229b52327
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e7cc68af4d5b53a36e9affc038951e2be63de90f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54954613"
---
# <a name="idebuggenericparamfield"></a>IDebugGenericParamField
表示托管的代码的泛型类型的参数。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugGenericParamField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 用于泛型的支持。  
  
## <a name="methods"></a>方法  
 除了上的方法[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口，此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[ConstraintCount](../../../extensibility/debugger/reference/idebuggenericparamfield-constraintcount.md)|返回与此泛型参数的约束的数目。|  
|[GetConstraints](../../../extensibility/debugger/reference/idebuggenericparamfield-getconstraints.md)|检索与此泛型参数的约束。|  
|[GetFlags](../../../extensibility/debugger/reference/idebuggenericparamfield-getflags.md)|检索此泛型参数的标志。|  
|[GetIndex](../../../extensibility/debugger/reference/idebuggenericparamfield-getindex.md)|检索此泛型参数的索引。|  
|[GetNameOfFormalParam](../../../extensibility/debugger/reference/idebuggenericparamfield-getnameofformalparam.md)|检索此泛型参数的名称。|  
|[GetOwner](../../../extensibility/debugger/reference/idebuggenericparamfield-getowner.md)|检索此泛型参数的类型或方法的所有者。|  
  
## <a name="requirements"></a>要求  
 标头：Sh.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll