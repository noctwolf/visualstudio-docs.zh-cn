---
title: 复制 （编程捕获） |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aab2b18c8c349211f4b5bd26b055d6ee5b65f0c6
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990943"
---
# <a name="copy-programmatic-capture"></a>复制（编程捕获）
将活动图形日志 (.vsglog) 文件的内容复制到新文件。  
  
## <a name="syntax"></a>语法  
  
```C++  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szNewVSGLog`  
 新图形日志文件的文件名。  
  
## <a name="remarks"></a>备注  
 若要将图形信息复制到新文件，您必须已捕获一些图形信息；否则，不会执行任何操作。