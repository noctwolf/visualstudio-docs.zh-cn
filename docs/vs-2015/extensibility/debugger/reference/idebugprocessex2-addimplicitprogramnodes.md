---
title: IDebugProcessEx2::AddImplicitProgramNodes |Microsoft Docs
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
- IDebugProcessEx2::AddImplicitProgramNodes
helpviewer_keywords:
- IDebugProcessEx2::AddImplicitProgramNodes method
ms.assetid: 8b491b00-f9e7-45b3-9115-fe58c3464289
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8b416fdfd3c3a08d028bb01945f2ceb02ae5f8e3
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733589"
---
# <a name="idebugprocessex2addimplicitprogramnodes"></a>IDebugProcessEx2::AddImplicitProgramNodes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此方法将添加指定每种调试引擎 (DE) 的程序节点。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT AddImplicitProgramNodes(  
   REFGUID guidLaunchingEngine,  
   GUID*   rgguidSpecificEngines,  
   DWORD   celtSpecificEngines  
);  
```  
  
```csharp  
int AddImplicitProgramNodes(  
   ref Guid guidLaunchingEngine,  
   Guid[]   rgguidSpecificEngines,  
   uint     celtSpecificEngines  
);  
```  
  
#### <a name="parameters"></a>参数  
 `guidLaunchingEngine`  
 [in]`GUID`的 DE 是要用来启动程序 （并且假定添加其自身程序节点）。  
  
 `rgguidSpecificEngines`  
 [in]数组`GUID`的 DEs 将节点添加的程序。  
  
 `celtSpecificEngines`  
 [in]数`GUID`中的 s`rgguidSpecificEngines`数组。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 [程序节点](../../../extensibility/debugger/program-nodes.md)中列出的每个 DE 将添加`rgguidSpecificEngines`— 不包括启动引擎 (中给出`guidLaunchingEngine`)，这假定它启动程序时添加其自己的程序节点。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramEx2](../../../extensibility/debugger/reference/idebugprogramex2.md)   
 [程序节点](../../../extensibility/debugger/program-nodes.md)

