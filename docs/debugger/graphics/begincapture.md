---
title: "BeginCapture |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e1c7c0f57b919271c4880c9c1f2fbd8ca1dc964f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="begincapture"></a>BeginCapture
开始将结尾的捕获时间间隔`EndCapture`。  
  
## <a name="syntax"></a>语法  
  
```C++  
void BeginCapture();  
```  
  
## <a name="remarks"></a>备注  
 捕获时间间隔通常跨越一个帧的子集，例如，当您仅需要捕获有关某种绘图调用的图形信息时。 如果捕获时间间隔跨越对 present 的调用，则将捕获图形信息的两个帧。 第一个帧跨越对 `BeginCapture` 的调用与对 present 的调用之间的时间间隔；第二个帧跨越对 present 调用后的第一个 Direct3D 和对 `EndCapture` 调用之间的时间间隔。  
  
 若要捕获时间间隔，你必须准备你的应用以捕获并记录图形信息 — 也就是说，你必须已调用[Init](init.md)的实例通过`VsgDbg`类你在调用之前`BeginCapture`或`EndCapture`。  
  
## <a name="see-also"></a>请参阅  
 [EndCapture](endcapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)