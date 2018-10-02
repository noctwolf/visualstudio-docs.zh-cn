---
title: IDebugEngine2::GetEngineID |Microsoft Docs
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
- IDebugEngine2::GetEngineID
helpviewer_keywords:
- IDebugEngine2::GetEngineID
ms.assetid: 0d5674c8-a9b9-4b72-8211-d2d68695775a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0326f165b31ab2597b01561fc2b86854eda04c61
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483179"
---
# <a name="idebugengine2getengineid"></a>IDebugEngine2::GetEngineID
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugEngine2::GetEngineID](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugengine2-getengineid)。  
  
获取调试引擎 (DE) 的 GUID。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetEngineID(   
   GUID* pguidEngine  
);  
```  
  
```csharp  
int GetEngineID(   
   out Guid pguidEngine  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pguidEngine`  
 [out]返回 DE 的 GUID。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 典型的 Guid 的一些示例包括`guidScriptEng`， `guidNativeEng`，或`guidSQLEng`。 新的调试引擎将创建其自己的标识的 GUID。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于简单`CEngine`对象，它实现[IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)接口。  
  
```cpp#  
HRESULT CEngine::GetEngineId(GUID *pguidEngine){    
   if (pguidEngine) {    
      // Set pguidEngine to guidBatEng, as defined in the Batdbg.idl file.    
      // Other languages would require their own guidDifferentEngine to be  
      //defined in the Batdbg.idl file.    
      *pguidEngine = guidBatEng;    
      return NOERROR; // This is typically S_OK.    
   } else {  
      return E_INVALIDARG;    
   }    
}    
```  
  
## <a name="see-also"></a>请参阅  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)

