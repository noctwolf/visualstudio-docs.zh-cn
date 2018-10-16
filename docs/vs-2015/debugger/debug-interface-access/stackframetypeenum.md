---
title: StackFrameTypeEnum |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb233000eb9bc0684858a82bf63ac2d71dbd60e5
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49252260"
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

指定的堆栈帧类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum StackFrameTypeEnum {  
   FrameTypeFPO,  
   FrameTypeTrap,  
   FrameTypeTSS,  
   FrameTypeStandard,  
   FrameTypeFrameData,  
   FrameTypeUnknown = -1  
};  
```  
  
## <a name="elements"></a>元素  
 `FrameTypeFPO`  
 帧指针省略;FPO 信息可用。  
  
 `FrameTypeTrap`  
 内核陷阱帧。  
  
 `FrameTypeTSS`  
 内核陷阱帧。  
  
 `FrameTypeStandard`  
 标准 EBP 堆栈帧。  
  
 `FrameTypeFrameData`  
 帧指针省略;帧数据信息可用。  
  
 `FrameTypeUnknown`  
 不具有任何调试信息的帧。  
  
## <a name="remarks"></a>备注  
 此枚举中的值返回通过调用[idiastackframe:: Get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： cvconst.h  
  
## <a name="see-also"></a>请参阅  
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)



