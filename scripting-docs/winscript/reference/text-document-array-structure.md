---
title: TEXT_DOCUMENT_ARRAY 结构 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- TEXT_DOCUMENT_ARRAY Structure
ms.assetid: 47c08f23-981b-4105-9240-6dfffc6cb91b
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ff283b52d15310304fb60c322bdb51c33ed33ac
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096936"
---
# <a name="textdocumentarray-structure"></a>TEXT_DOCUMENT_ARRAY 结构
一个数组[IDebugDocumentText 接口](../../winscript/reference/idebugdocumenttext-interface.md)对象。 使用 CoTaskMemAlloc 分配成员。  
  
## <a name="syntax"></a>语法  
  
```cpp
typedef struct tagTEXT_DOCUMENT_ARRAY{    DWORD dwCount;    [size_is(dwCount)] IDebugDocumentText **Members;} TEXT_DOCUMENT_ARRAY;  
```  
  
## <a name="members"></a>成员  
 `dwCount`  
 文档数。  
  
 `Members`  
 文档集。  
  
## <a name="see-also"></a>请参阅  
 [活动脚本调试器常量、枚举和结构](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)