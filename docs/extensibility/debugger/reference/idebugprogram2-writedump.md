---
title: IDebugProgram2::WriteDump |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::WriteDump
helpviewer_keywords:
- IDebugProgram2::WriteDump
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d7282a7bd57397f6dc1a09dac44dfb0cdfcf9078
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53915963"
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
将转储写入到一个文件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT WriteDump(   
   DUMPTYPE  DumpType,  
   LPCOLESTR pszDumpUrl  
);  
```  
  
```csharp  
int WriteDump(   
   enum_DUMPTYPE  DumpType,  
   string         pszDumpUrl  
);  
```  
  
#### <a name="parameters"></a>参数  
 `DumpType`  
 [in]中的值[DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md)枚举，用于指定的转储，类型，例如，简单地说或长时间。  
  
 `pszDumpUrl`  
 [in]要写入转储的 URL。 通常，这是中的窗体`file://c:\path\filename.ext`，但可能是任何有效的 URL。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 程序转储通常将包括当前堆栈帧，堆栈本身，在该程序，并且可能是任何程序拥有的内存中运行的线程的列表。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)