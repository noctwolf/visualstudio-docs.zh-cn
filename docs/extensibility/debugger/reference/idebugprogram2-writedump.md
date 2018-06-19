---
title: IDebugProgram2::WriteDump |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 0b17d75ace19ac53cbcd229d7c15de573c1ecb8b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31114503"
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
转储写入文件。  
  
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
 [in]取值范围为[DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md)枚举，它指定的一种转储，例如、 short 或 long 类型的值。  
  
 `pszDumpUrl`  
 [in]要写入到转储的 URL。 通常，这是形式`file://c:\path\filename.ext`，但可能是任何有效的 URL。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 程序转储通常将包括当前堆栈帧，堆栈本身、 运行程序，并可能程序拥有任何内存中的线程的列表。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)