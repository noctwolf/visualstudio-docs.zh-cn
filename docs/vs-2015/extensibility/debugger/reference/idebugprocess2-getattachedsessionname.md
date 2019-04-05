---
title: IDebugProcess2::GetAttachedSessionName | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 39975163cdddf06ba87add52e60c9a81581985ab
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58934803"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取正在调试此进程的会话的名称。 IDE 可以调试特定计算机上的特定进程的用户显示此信息。  
  
> [!NOTE]
>  此方法已弃用，并且它的实现应始终返回`E_NOTIMPL`。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetAttachedSessionName(  
   BSTR* pbstrSessionName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrSessionName`  
  
## <a name="return-value"></a>返回值  
 此方法应始终返回`E_NOTIMPL`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)
