---
title: "CaptureCurrentFrame |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 739f2a9a97fefcb1bc57c7987d5afec7a09ff4ad
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
将当前帧的剩余部分捕获到图形日志文件。  
  
## <a name="syntax"></a>语法  
  
```C++  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>备注  
 如果另一个捕获当前正在进行中（例如，通过 `BeginCapture` 函数启动的捕获），则将完成该捕获并将其记录到图形日志以作为不同的帧。 紧跟着，图形诊断开始捕获当前帧的剩余部分，此部分也记录为不同的帧。 通过调用 present 来标记当前帧的结尾。  
  
 若要捕获帧，必须准备好你的应用以捕获并记录图形信息 — 也就是说，你必须已调用[Init](init.md)的实例通过`VsgDbg`类你在调用之前`CaptureCurrentFrame`。  
  
## <a name="see-also"></a>请参阅  
 [Init](init.md)   
 [BeginCapture](begincapture.md)