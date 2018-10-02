---
title: EncUnavailableReason |Microsoft Docs
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
- EncUnavailableReason
helpviewer_keywords:
- EncUnavailableReason enumeration
ms.assetid: c10aa4c0-d7e0-4de1-b8ff-7e050985eb12
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 531d6587593db01ac1536b3111633721f4ee84f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468940"
---
# <a name="encunavailablereason"></a>EncUnavailableReason
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[EncUnavailableReason](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/encunavailablereason)。  
  
`This is for internal use only!` 表示原因，**编辑并继续**不可用。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum tagEncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
typedef enum tagEncUnavailableReason EncUnavailableReason;  
```  
  
```csharp  
public enum EncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
```  
  
#### <a name="parameters"></a>参数  
 ENCUN_NONE  
 编辑并继续不可用的原因没有特定原因。  
  
 ENCUN_INTEROP  
 编辑并继续的互操作调用期间不可用。  
  
 ENCUN_SQLCLR  
 编辑并继续在使用公共语言运行时 (CLR) 的 SQL 过程调用期间不可用。  
  
 ENCUN_MINIDUMP  
 编辑并继续处理小型转储时不可用。  
  
 ENCUN_EMBEDDED  
 处理嵌入的代码时，编辑并继续不可用。  
  
 ENCUN_ATTACH  
 编辑并继续就不可用会话已附加到，因为不会启动的调试器。  
  
 ENCUN_WIN64  
 编辑并继续处理 64 位 Windows 代码时不可用。  
  
## <a name="remarks"></a>备注  
 此枚举仅适用于内部使用通过[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]。 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)并[DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)由自定义端口提供程序实现的方法应始终返回`E_NOTIMPL`。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.idl  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)   
 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)

