---
title: 复制 （编程捕获） |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30ec235a-0abb-44b9-8852-61bc9e67ce22
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7ec5c95a2419e465f93f7d11045672de2f1b0174
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49293184"
---
# <a name="copy-programmatic-capture"></a>复制（编程捕获）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

将活动图形日志 (.vsglog) 文件的内容复制到新文件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void Copy(  
  wchar_t const * szNewVSGLog  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szNewVSGLog`  
 新图形日志文件的文件名。  
  
## <a name="remarks"></a>备注  
 若要将图形信息复制到新文件，您必须已捕获一些图形信息；否则，不会执行任何操作。



