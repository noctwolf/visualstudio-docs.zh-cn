---
title: EncUnavailableReason |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EncUnavailableReason
helpviewer_keywords:
- EncUnavailableReason enumeration
ms.assetid: c10aa4c0-d7e0-4de1-b8ff-7e050985eb12
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4dcf705015925145b790b14a44007fed8d8fad3b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101766"
---
# <a name="encunavailablereason"></a>EncUnavailableReason
`This is for internal use only!` 表示原因，**编辑并继续**不可用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
 没有特定原因，编辑并继续不可用的原因。  
  
 ENCUN_INTEROP  
 编辑并继续在互操作调用期间不可用。  
  
 ENCUN_SQLCLR  
 编辑并继续在使用公共语言运行时 (CLR) 的 SQL 过程调用期间不可用。  
  
 ENCUN_MINIDUMP  
 编辑并继续处理一个小型转储时不可用。  
  
 ENCUN_EMBEDDED  
 处理嵌入的代码时，编辑并继续不可用。  
  
 ENCUN_ATTACH  
 编辑并继续就不可用因为会话已附加到，不会启动的调试器。  
  
 ENCUN_WIN64  
 编辑并继续处理 64 位 Windows 编码时不可用。  
  
## <a name="remarks"></a>备注  
 此枚举仅适用于内部使用通过[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]。 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)和[DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)方法的自定义端口供应商提供的实施方式应始终返回`E_NOTIMPL`。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.idl  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)   
 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)