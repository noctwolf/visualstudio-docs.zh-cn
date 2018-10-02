---
title: IDebugProperty2::GetReference |Microsoft Docs
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
- IDebugProperty2::GetReference
helpviewer_keywords:
- IDebugProperty2::GetReference method
ms.assetid: 2fa97d9b-c3d7-478e-ba5a-a933f40a0103
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 22d187fb8e5f3c2fd869de5f6472d0e761dd8c8e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468777"
---
# <a name="idebugproperty2getreference"></a>IDebugProperty2::GetReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProperty2::GetReference](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty2-getreference)。  
  
返回对该属性的值的引用。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetReference(  
   IDebugReference2** ppReference  
);  
```  
  
```csharp  
int GetReference(  
   out IDebugReference2 ppReference  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppRererence`  
 [out]返回[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)对象，表示对属性的值的引用。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码，通常`E_NOTIMPL`或`E_GETREFERENCE_NO_REFERENCE`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)

