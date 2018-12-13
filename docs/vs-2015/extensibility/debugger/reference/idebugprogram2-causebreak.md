---
title: IDebugProgram2::CauseBreak |Microsoft Docs
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
- IDebugProgram2::CauseBreak
helpviewer_keywords:
- IDebugProgram2::CauseBreak
ms.assetid: 07d353fc-68ab-4297-a18f-3d3c7a80e121
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0ace26055a9d82ff3907003168becdbd00632a7d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51782747"
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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

