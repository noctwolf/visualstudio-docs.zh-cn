---
title: IDebugMessageEvent2::GetMessage |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMessageEvent2::GetMessage
helpviewer_keywords:
- GetMessage method
- IDebugMessageEvent2::GetMessage method
ms.assetid: 9fca7285-f7f1-422d-8565-92bf0e0db60a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a00f7019a96696b0c1bde6876697b71d96c253d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31111867"
---
# <a name="idebugmessageevent2getmessage"></a>IDebugMessageEvent2::GetMessage
获取要显示的消息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMessage(   
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrMessage,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetMessage(   
   out enum_MESSAGETYPE pMessageType,  
   out string           pbstrMessage,  
   out uint             pdwType,  
   out string           pbstrHelpFileName,  
   out uint             dwHelpId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pMessageType`  
 [out]返回一个值从[MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)描述消息的类型的枚举。  
  
 `pbstrMessage`  
 [out]返回的消息。  
  
 `pdwType`  
 [out]返回使用 Win32 的约定的消息的类型`MessageBox`函数。 请参阅[AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox)有关详细信息的函数。  
  
 `pbstrHelpFileName`  
 [在中，out]返回的帮助文件名称。 如果没有帮助文件可能是 null （c + +） 或空值 (C#)。  
  
 `pdwHelpId`  
 [在中，out]返回帮助标识符。 可能是 0，如果没有帮助与此消息关联。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)   
 [AfxMessageBox](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox)