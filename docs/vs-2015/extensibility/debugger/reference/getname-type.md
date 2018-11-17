---
title: GETNAME_TYPE |Microsoft Docs
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
- GETNAME_TYPE
helpviewer_keywords:
- GETNAME_TYPE enumeration
ms.assetid: 2f9f1679-e9e8-4c9c-ac90-aa07bfe69914
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8edbf690851d820adc2fc8fdb61044aa9c9d46e2
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51725030"
---
# <a name="getnametype"></a>GETNAME_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定要从中检索文件的名称类型。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum enum_GETNAME_TYPE {   
   GN_NAME         = 0,  
   GN_FILENAME     = 1,  
   GN_BASENAME     = 2,  
   GN_MONIKERNAME  = 3,  
   GN_URL          = 4,  
   GN_TITLE        = 5,  
   GN_STARTPAGEURL = 6  
};  
typedef DWORD GETNAME_TYPE;  
```  
  
```csharp  
public enum enum_GETNAME_TYPE {   
   GN_NAME         = 0,  
   GN_FILENAME     = 1,  
   GN_BASENAME     = 2,  
   GN_MONIKERNAME  = 3,  
   GN_URL          = 4,  
   GN_TITLE        = 5,  
   GN_STARTPAGEURL = 6  
};  
```  
  
## <a name="members"></a>成员  
 GN_NAME  
 指定文档或上下文的友好的名称。  
  
 GN_FILENAME  
 指定文档或上下文的完整的路径。  
  
 GN_BASENAME  
 指定的基文件名而不是文档或上下文的完整路径。  
  
 GN_MONIKERNAME  
 名字对象的形式指定文档或上下文的唯一的名称。  
  
 GN_URL  
 指定文档或上下文 URL 的名称。  
  
 GN_TITLE  
 如果存在，请指定文档的标题。  
  
 GN_STARTPAGEURL  
 获取进程的起始页 URL。  
  
## <a name="remarks"></a>备注  
 这些值作为参数传递[GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)， [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)，并[GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)方法，以指定名称返回的类型。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)   
 [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)   
 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)

