---
title: IDebugPortEx2::GetPortProcessId |Microsoft Docs
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
- IDebugPortEx2::GetPortProcessId
helpviewer_keywords:
- IDebugPortEx2::GetPortProcessId
ms.assetid: be85be66-47e6-415f-b0ca-24599aa5f13c
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a34c2a3d825756b34b69cfffc9d76bde76f125ec
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51735324"
---
# <a name="idebugportex2getportprocessid"></a>IDebugPortEx2::GetPortProcessId
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取自身的端口的进程 ID。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetPortProcessId (   
   DWORD* pdwProcessId  
);  
```  
  
```csharp  
int GetPortProcessId (   
   out uint pdwProcessId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwProcessId`  
 [out]返回自身的端口的物理进程 ID。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 Win32 运行时中，此方法通常会调用 Win32 函数`GetCurrentProcessId`以获取物理进程 id。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortEx2](../../../extensibility/debugger/reference/idebugportex2.md)

