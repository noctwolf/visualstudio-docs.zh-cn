---
title: 概述 （调试接口访问 SDK） |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined types
- .dbg files
- modules
- interfaces [DIA SDK]
- DBG files
- procedures [DIA SDK]
- executable files
- COM objects, in DIA SDK
- compilands
- executable images
ms.assetid: 720b4479-a8bc-4fec-860e-80c1a0780405
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f159dcc58a096033516fdd272819b9eb1ad916d1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922647"
---
# <a name="overview-debug-interface-access-sdk"></a>概述（调试接口访问 SDK）
DIA SDK 用于访问 Microsoft 调试信息。 DIA SDK 提供了基于 COM 的 API 集，消除了需要重写代码，当 Microsoft 发生更改时的调试信息的格式。 DIA SDK 还允许您从以前版本的调试信息，位于由生成的.pdb 和.dbg 文件中的选定的一组读取[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]5.0 及更高版本。  
  
 DIA SDK 中的每个接口表示不同的 COM 对象，除外，其中另有说明。 其他接口，因此其他对象，创建和通过显式查询，如[idiadatasource:: Opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)或[idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)，而不是通过调用`QueryInterface`上现有的接口指针。  
  
## <a name="see-also"></a>请参阅  
 [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)