---
title: COMPUTER_INFO |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- COMPUTER_INFO structure
ms.assetid: 943085b2-f165-462d-9a4e-2086f0cdfff4
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4a50fd8e0afb9a5ce00534d9aee397ff680fa46d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468795"
---
# <a name="computerinfo"></a>COMPUTER_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[COMPUTER_INFO](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/computer-info)。  
  
描述在其运行调试器的计算机。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
typedef struct tagCOMPUTER_INFO  
{  
    WORD wProcessorArchitecture;  
    WORD wSuiteMask;  
    DWORD dwOperatingSystemVersion;  
} COMPUTER_INFO;  
```  
  
```csharp  
public struct COMPUTER_INFO  
{  
    public ushort wProcessorArchitecture;  
    public ushort wSuiteMask;  
    public uint dwOperatingSystemVersion;  
}  
```  
  
## <a name="terms"></a>术语  
 wProcessorArchitecture  
 标识微处理器体系的结构。  
  
 wSuiteMask  
 标识套件掩码。  
  
 dwOperatingSystemVersion  
 操作系统版本号。  
  
## <a name="remarks"></a>备注  
 返回此结构[GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetComputerInfo](../../../extensibility/debugger/reference/idebugwindowscomputerport2-getcomputerinfo.md)

