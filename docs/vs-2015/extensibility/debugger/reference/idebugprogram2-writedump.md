---
title: IDebugProgram2::WriteDump |Microsoft Docs
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
- IDebugProgram2::WriteDump
helpviewer_keywords:
- IDebugProgram2::WriteDump
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8708751820ca70386e6c9927105384eee9a96a15
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480633"
---
# <a name="idebugprogram2writedump"></a>IDebugProgram2::WriteDump
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProgram2::WriteDump](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-writedump)。  
  
将转储写入到一个文件。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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

