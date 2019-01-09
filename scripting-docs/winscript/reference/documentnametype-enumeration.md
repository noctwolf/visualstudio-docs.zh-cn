---
title: DOCUMENTNAMETYPE 枚举 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DOCUMENTNAMETYPE
apilocation:
- scrobj.dll
helpviewer_keywords:
- DOCUMENTNAMETYPE enumeration
ms.assetid: d36d550e-efb4-493d-8971-4de267005654
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31e304cfbb0ed7cd19b832d7ed7c33ccc2c930c3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094765"
---
# <a name="documentnametype-enumeration"></a>DOCUMENTNAMETYPE 枚举
描述为文档获取哪种类型。  
  
## <a name="syntax"></a>语法  
  
```cpp
typedef enum tagDOCUMENTNAMETYPE {  
   DOCUMENTNAMETYPE_APPNODE,  
   DOCUMENTNAMETYPE_TITLE,  
   DOCUMENTNAMETYPE_FILE_TAIL,  
   DOCUMENTNAMETYPE_URL,  
DOCUMENTNAMETYPE_UNIQUE_TITLE,} DOCUMENTNAMETYPE;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|DOCUMENTNAMETYPE_APPNODE|显示在应用程序树中获取的名称。|  
|DOCUMENTNAMETYPE_TITLE|在查看器标题栏上显示获取的名称。|  
|DOCUMENTNAMETYPE_FILE_TAIL|获取不含路径的文件名称。|  
|DOCUMENTNAMETYPE_URL|获取文档的 URL。|  
|DOCUMENTNAMETYPE_UNIQUE_TITLE|获取附加的标识的枚举的标题。|  
  
## <a name="see-also"></a>请参阅  
 [活动脚本调试器常量、枚举和结构](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)