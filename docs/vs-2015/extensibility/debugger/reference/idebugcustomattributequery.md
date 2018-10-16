---
title: IDebugCustomAttributeQuery |Microsoft Docs
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
- IDebugCustomAttributeQuery interface
ms.assetid: b804b619-70eb-4c38-80d9-c8b32b65ed3e
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b1ffb957f15611562011b7d147a8388f09f11558
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49208190"
---
# <a name="idebugcustomattributequery"></a>IDebugCustomAttributeQuery
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

表示对方法或类型的自定义属性的查询。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugCustomAttributeQuery : IUnknown  
```  
  
## <a name="methods"></a>方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[GetCustomAttributeByName](../../../extensibility/debugger/reference/idebugcustomattributequery-getcustomattributebyname.md)|检索在给定其名称的自定义属性。|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery-iscustomattributedefined.md)|确定指定中定义自定义属性。|  
  
## <a name="requirements"></a>要求  
 标头： Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

