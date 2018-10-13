---
title: IDebugGenericFieldDefinition |Microsoft Docs
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
- IDebugGenericFieldDefinition interface
ms.assetid: b5a853b7-221e-4d62-8948-07423089d75d
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ee253ac5f51e71e1fc58d41fe44a6b76473722c6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49289648"
---
# <a name="idebuggenericfielddefinition"></a>IDebugGenericFieldDefinition
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

表示托管的代码的泛型类型的字段的定义。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugGenericFieldDefinition : IUnknown  
```  
  
## <a name="methods"></a>方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[ConstructInstantiation](../../../extensibility/debugger/reference/idebuggenericfielddefinition-constructinstantiation.md)|构造给定类型的参数数组的字段实例。|  
|[GetFormalTypeParams](../../../extensibility/debugger/reference/idebuggenericfielddefinition-getformaltypeparams.md)|检索给定的参数数目的类型参数。|  
|[TypeParamCount](../../../extensibility/debugger/reference/idebuggenericfielddefinition-typeparamcount.md)|检索与通用字段关联的类型参数的数目。|  
  
## <a name="requirements"></a>要求  
 标头： Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

