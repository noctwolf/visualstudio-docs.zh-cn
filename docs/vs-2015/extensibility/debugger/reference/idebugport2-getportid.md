---
title: IDebugPort2::GetPortId |Microsoft Docs
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
- IDebugPort2::GetPortId
helpviewer_keywords:
- IDebugPort2::GetPortId
ms.assetid: 837cb924-c113-4224-aa86-3e02b33dfa70
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d09cbd477c645de051589a9501607ac355138709
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49221307"
---
# <a name="idebugport2getportid"></a>IDebugPort2::GetPortId
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取端口标识符。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetPortId(   
   GUID* pguidPort  
);  
```  
  
```csharp  
int GetPortId(   
   out Guid pguidPort  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pguidPort`  
 [out]返回标识该端口的 GUID。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)

