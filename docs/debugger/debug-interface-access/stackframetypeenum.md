---
title: StackFrameTypeEnum |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- StackFrameTypeEnum enumeration
ms.assetid: 61e40163-eee0-4c1f-af47-cef3771bdc41
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 329661e857859a1f6452506ba2984ac962bf4ff2
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31470811"
---
# <a name="stackframetypeenum"></a>StackFrameTypeEnum
指定的堆栈帧类型。  
  
## <a name="syntax"></a>语法  
  
```C++  
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
 框架指针省略;FPO 信息可用。  
  
 `FrameTypeTrap`  
 内核陷阱帧。  
  
 `FrameTypeTSS`  
 内核陷阱帧。  
  
 `FrameTypeStandard`  
 标准 EBP 堆栈帧。  
  
 `FrameTypeFrameData`  
 框架指针省略;帧数据信息可用。  
  
 `FrameTypeUnknown`  
 没有任何调试信息的帧。  
  
## <a name="remarks"></a>备注  
 此枚举中的值返回通过调用[idiastackframe:: Get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： cvconst.h  
  
## <a name="see-also"></a>请参阅  
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackFrame::get_type](../../debugger/debug-interface-access/idiastackframe-get-type.md)