---
title: IEnumDebugPortSuppliers2::GetCount |Microsoft Docs
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
- IEnumDebugPortSuppliers2::GetCount
helpviewer_keywords:
- IEnumDebugPortSuppliers2::GetCount
ms.assetid: 004f78dd-87d0-41a8-bcaa-f7fadbfeb8fc
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 47a8582a69ca508bde1527cc074c9e1096461974
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49186534"
---
# <a name="ienumdebugportsuppliers2getcount"></a>IEnumDebugPortSuppliers2::GetCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

枚举中返回元素的数。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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
 此方法不是惯用的 COM 枚举接口，只有指定的一部分`Next`， `Clone`， `Skip`，和`Reset`方法需要实现。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)

