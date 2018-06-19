---
title: 文件状态代码枚举器 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- named constants, SccStatus enumerator
- source control plug-ins, file status enumeration
- SccStatus enumerator
- file status code enumerator
ms.assetid: 5c37876b-c83c-4ca1-837b-57cd465a879a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b3415440c80fcaa88edbecee924a118f82a9dd99
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128159"
---
# <a name="file-status-code-enumerator"></a>文件状态代码枚举器
`SccStatus`枚举器包含在源代码管理系统中指定的文件的状态的命名常量值。 此枚举由[SccQueryInfo](../extensibility/sccqueryinfo-function.md)和`POPLISTFUNC`回调函数 (请参阅[POPLISTFUNC](../extensibility/poplistfunc.md)有关详细信息)。  
  
## <a name="syntax"></a>语法  
  
```  
enum SccStatus {  
   SCC_STATUS_INVALID          = -1L,  
   SCC_STATUS_NOTCONTROLLED    = 0x0000L,  
   SCC_STATUS_CONTROLLED       = 0x0001L,  
   SCC_STATUS_CHECKEDOUT       = 0x0002L,  
   SCC_STATUS_OUTOTHER         = 0x0004L,  
   SCC_STATUS_OUTEXCLUSIVE     = 0x0008L,  
   SCC_STATUS_OUTMULTIPLE      = 0x0010L,  
   SCC_STATUS_OUTOFDATE        = 0x0020L,  
   SCC_STATUS_DELETED          = 0x0040L,  
   SCC_STATUS_LOCKED           = 0x0080L,  
   SCC_STATUS_MERGED           = 0x0100L,  
   SCC_STATUS_SHARED           = 0x0200L,  
   SCC_STATUS_PINNED           = 0x0400L,  
   SCC_STATUS_MODIFIED         = 0x0800L,  
   SCC_STATUS_OUTBYUSER        = 0x1000L  
   SCC_STATUS_NOMERGE          = 0x2000L  
   SCC_STATUS_RESERVED_1       = 0x4000L  
   SCC_STATUS_RESERVED_2       = 0x8000L  
};  
```  
  
## <a name="members"></a>成员  
 SCC_STATUS_INVALID  
 无法获取状态;不要依赖于它。  
  
 SCC_STATUS_NOTCONTROLLED  
 文件不在源代码管理下。  
  
 SCC_STATUS_CONTROLLED  
 文件是在源代码管理下。  
  
 SCC_STATUS_CHECKEDOUT  
 由本地磁盘上的当前用户签出。  
  
 SCC_STATUS_OUTOTHER  
 文件已由另一个用户签出。  
  
 SCC_STATUS_OUTEXCLUSIVE  
 文件以独占方式签出。  
  
 SCC_STATUS_OUTMULTIPLE  
 文件已由多个用户签出。  
  
 SCC_STATUS_OUTOFDATE  
 文件不是最新的。  
  
 SCC_STATUS_DELETED  
 文件已从项目中删除。  
  
 SCC_STATUS_LOCKED  
 文件被锁定;不允许的多个版本。  
  
 SCC_STATUS_MERGED  
 已合并文件，但尚不固定/验证。  
  
 SCC_STATUS_SHARED  
 项目之间共享文件。  
  
 SCC_STATUS_PINNED  
 文件共享到显式的版本。  
  
 SCC_STATUS_MODIFIED  
 文件已修改/已中断/违反。  
  
 SCC_STATUS_OUTBYUSER  
 文件已由当前用户签出。  
  
 SCC_STATUS_NOMERGE  
 文件永远不会与合并和无需在 GET 之前保存。  
  
 SCC_STATUS_RESERVED_1  
 保留以供内部使用。  
  
 SCC_STATUS_RESERVED_2  
 保留以供内部使用。  
  
## <a name="see-also"></a>另请参阅  
 [源控件插件](../extensibility/source-control-plug-ins.md)   
 [SccQueryInfo](../extensibility/sccqueryinfo-function.md)   
 [POPLISTFUNC](../extensibility/poplistfunc.md)