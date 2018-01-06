---
title: "复制 （编程捕获） |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7f8fce1893363ac6df0e6d22320f718833a1114e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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