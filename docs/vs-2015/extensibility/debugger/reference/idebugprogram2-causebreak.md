---
title: IDebugProgram2::CauseBreak |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProgram2::CauseBreak
helpviewer_keywords:
- IDebugProgram2::CauseBreak
ms.assetid: 07d353fc-68ab-4297-a18f-3d3c7a80e121
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a1bfd8c2094c6ef9d961eb5375aae7cf5c6d13da
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471459"
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProgram2::CauseBreak](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-causebreak)。  
  
请求程序停止执行下一步的时间运行其线程尝试之一。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT CauseBreak(   
   void   
);  
```  
  
```csharp  
int CauseBreak();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)时接下来，该程序尝试调用此方法之后，运行代码，则会发送事件。  
  
 此方法是异步的方法将立即返回而不一定等待程序停止。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)

