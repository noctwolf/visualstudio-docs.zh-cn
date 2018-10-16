---
title: IDebugEngineLaunch2::ResumeProcess |Microsoft Docs
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
- IDebugEngineLaunch2::ResumeProcess
helpviewer_keywords:
- IDebugEngineLaunch2::ResumeProcess
ms.assetid: 61ccc14e-75c6-44e7-aae4-57a9aac52089
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2d4d0c0865ea19ade6a268abfa40327b3714b453
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49186207"
---
# <a name="idebugenginelaunch2resumeprocess"></a>IDebugEngineLaunch2::ResumeProcess
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

恢复进程执行。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT ResumeProcess (   
   IDebugProcess2* pProcess  
);  
```  
  
```csharp  
int ResumeProcess (   
   IDebugProcess2 pProcess  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pProcess`  
 [in][IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)对象，表示要恢复的过程。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。  
  
## <a name="remarks"></a>备注  
 已通过调用启动进程后调用此方法[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)

