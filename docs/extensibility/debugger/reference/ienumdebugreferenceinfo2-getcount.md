---
title: "IEnumDebugReferenceInfo2::GetCount |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugReferenceInfo2::GetCount
helpviewer_keywords: IEnumDebugReferenceInfo2::GetCount
ms.assetid: e62706e0-d2cd-48fb-8fdf-444463c651ab
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f94148845d23407477b10053cc5f9ef9128b6aac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugreferenceinfo2getcount"></a>IEnumDebugReferenceInfo2::GetCount
枚举中返回元素的数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCount(  
   ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pcelt`  
 [out]枚举中返回元素的数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法不是指定仅通常 COM 枚举接口的一部分`Next`， `Clone`， `Skip`，和`Reset`方法需要实现。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)