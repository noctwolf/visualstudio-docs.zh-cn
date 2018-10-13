---
title: AddMessage |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b60f8bac24b01e39327357b89e9e96c04765077
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49248997"
---
# <a name="addmessage"></a>AddMessage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

将自定义消息添加到图形诊断*HUD* （显示）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szMessage`  
 要添加到 HUD 的消息。  
  
## <a name="remarks"></a>备注  
 图像诊断 HUD 显示在正在图形诊断下运行的应用的左上角。 它显示有关此应用和图形信息捕获的信息以及通过调用此函数添加的消息。  
  
 若要将消息添加到 HUD，您不必主动捕获图形信息-也就是说，通过的实例添加消息`VsgDbg`类，但[Init](../debugger/init.md)成员函数执行的操作不以首先调用。 消息只显示在 HUD 中，而不会记录在图形日志文件中。



