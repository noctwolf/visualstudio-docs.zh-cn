---
title: IEnumDebugPropertyInfo2::Reset |Microsoft Docs
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
- IEnumDebugPropertyInfo2::Reset
helpviewer_keywords:
- IEnumDebugPropertyInfo2::Reset
ms.assetid: fa4201c1-4633-4596-93aa-bd415c4ed71a
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 01b67d902c963eababcf34a577c95f8b397344fe
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49219305"
---
# <a name="ienumdebugpropertyinfo2reset"></a>IEnumDebugPropertyInfo2::Reset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

将枚举重置为第一个元素。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法下, 一步调用后[下一步](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md)方法返回的第一个元素的枚举。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)

