---
title: IDebugProgramHost2::GetHostName |Microsoft Docs
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
- IDebugProgramHost2::GetHostName
helpviewer_keywords:
- IDebugProgramHost2::GetHostName
ms.assetid: 48bbb089-e59a-471a-9965-24b42a8dabf3
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1d19901134de6cf33d0b15f6fe65cc379662ec58
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807449"
---
# <a name="idebugprogramhost2gethostname"></a>IDebugProgramHost2::GetHostName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取标题、 友好名称或此程序的宿主进程的文件名。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetHostName(   
   DWORD dwType,  
   BSTR* pbstrHostName  
);  
```  
  
```csharp  
int GetHostName(   
   uint dwType,  
   out string pbstrHostName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwType`  
 [in]中的值[GETHOSTNAME_TYPE](../../../extensibility/debugger/reference/gethostname-type.md)枚举。  
  
 `pbstrHostName`  
 [out]返回宿主进程的请求的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 在此方法的典型实现`dwType`忽略参数和返回主机计算机的友好名称。 另一个可能的实现是传递`dwType`的调用的参数[GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)方法获取的名称。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)

