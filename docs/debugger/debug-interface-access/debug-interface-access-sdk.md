---
title: 调试接口访问 SDK |Microsoft Docs
ms.date: 07/24/2018
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [DIA SDK]
- debugger [DIA SDK]
- DIA SDK
ms.assetid: 4c0abe53-11d3-4b7a-bdc7-b054f85aaf40
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 161934d30c7cd4ecb9d2658e7dac12e46049be1a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54932293"
---
# <a name="debug-interface-access-sdk"></a>调试接口访问 SDK

Microsoft 调试接口访问软件开发工具包 (DIA SDK) 提供了调试信息存储在由 Microsoft 后置编译器工具生成的程序数据库 (.pdb) 文件的访问权限。 后置编译器工具生成的.pdb 文件的格式进行常量修订版本，因为公开格式是不切实际的。 使用 DIA API，可以开发应用程序的搜索和浏览存储在.pdb 文件中的调试信息。 此类应用程序，例如，报告堆栈跟踪信息和分析性能数据。

## <a name="in-this-section"></a>本节内容

[入门](../../debugger/debug-interface-access/getting-started-debug-interface-access-sdk.md)  
概述了 DIA SDK 功能，并指定 DIA SDK 以及必需的标头和库文件的安装。

[查询 .Pdb 文件](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
说明了如何使用 DIA API 来查询.pdb 文件。

[符号和符号标记](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)  
讨论如何在 DIA API 中使用符号和符号标记。

[引用](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)  
包含接口、 方法、 枚举和结构 DIA API。

[Dia2dump 示例](../../debugger/debug-interface-access/dia2dump-sample.md)  
说明了如何使用 DIA API 来搜索和浏览的调试信息。
