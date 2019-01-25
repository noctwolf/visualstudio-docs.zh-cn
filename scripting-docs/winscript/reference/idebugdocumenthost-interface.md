---
title: IDebugDocumentHost 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentHost interface
ms.assetid: 2fed4220-b6a2-47c6-bf28-daad7dd5c42d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 46684bf2264813a8daaa466b98119496ba85d4b9
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346535"
---
# <a name="idebugdocumenthost-interface"></a>IDebugDocumentHost 接口
公开特定于宿主的功能，如语法着色，到调试器。 `IDebugDocumentHelper::SetDebugDocumentHost`方法采用此接口作为参数。  
  
 除了继承的方法之外`IUnknown`，则`IDebugDocumentHost`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugDocumentHost::GetDeferredText](../../winscript/reference/idebugdocumenthost-getdeferredtext.md)|返回添加的使用的字符范围`IDebugDocumentHelper::AddDeferredText`，原始主机文档中。|  
|[IDebugDocumentHost::GetScriptTextAttributes](../../winscript/reference/idebugdocumenthost-getscripttextattributes.md)|返回的文档文本块的文本属性。|  
|[IDebugDocumentHost::OnCreateDocumentContext](../../winscript/reference/idebugdocumenthost-oncreatedocumentcontext.md)|通知宿主，新的文档上下文创建，并使宿主可以选择性地返回控制新的上下文的对象。|  
|[IDebugDocumentHost::GetPathName](../../winscript/reference/idebugdocumenthost-getpathname.md)|返回文档的源文件的完整路径 （包括文件名）。|  
|[IDebugDocumentHost::GetFileName](../../winscript/reference/idebugdocumenthost-getfilename.md)|返回的文档，不包含路径信息的名称。|  
|[IDebugDocumentHost::NotifyChanged](../../winscript/reference/idebugdocumenthost-notifychanged.md)|通知宿主已保存文档的源文件，并应刷新其内容。|