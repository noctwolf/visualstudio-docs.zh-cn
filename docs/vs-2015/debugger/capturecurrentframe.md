---
title: CaptureCurrentFrame |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: 8
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76dca819f6a6a236f3b0e206dd0585cebce3f25e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51764421"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

将当前帧的剩余部分捕获到图形日志文件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>备注  
 如果另一个捕获当前正在进行中（例如，通过 `BeginCapture` 函数启动的捕获），则将完成该捕获并将其记录到图形日志以作为不同的帧。 紧跟着，图形诊断开始捕获当前帧的剩余部分，此部分也记录为不同的帧。 通过调用 present 来标记当前帧的结尾。  
  
 若要捕获帧，您必须准备应用以捕获并记录图形信息-也就是说，您必须具有名为[Init](../debugger/init.md)的实例通过`VsgDbg`类，然后调用`CaptureCurrentFrame`。  
  
## <a name="see-also"></a>请参阅  
 [Init](../debugger/init.md)   
 [BeginCapture](../debugger/begincapture.md)



