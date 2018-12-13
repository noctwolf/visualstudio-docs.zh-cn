---
title: EncUnavailableReason |Microsoft Docs
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
ms.openlocfilehash: 8228d741848ba90c2d2d39618781e6d915c4b627
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49854645"
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
 此枚举仅适用于内部使用通过[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]。 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)并[DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)由自定义端口提供程序实现的方法应始终返回`E_NOTIMPL`。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.idl  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)   
 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)