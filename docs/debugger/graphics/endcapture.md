---
title: EndCapture |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 06084c3b-e065-49b6-968e-d578762fb871
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 27fc4053fdfbfe767e72b9b5511ab3660cd7b4b8
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="endcapture"></a>EndCapture
结束以 `BeginCapture` 开始的捕获时间间隔。  
  
## <a name="syntax"></a>语法  
  
```C++  
void EndCapture();  
```  
  
## <a name="remarks"></a>备注  
 捕获时间间隔通常跨越一个帧的子集，例如，当您仅需要捕获有关某种绘图调用的图形信息时。 如果捕获时间间隔跨越对 present 的调用，则将捕获图形信息的两个帧。 第一个帧跨越对 `BeginCapture` 的调用与对 present 的调用之间的时间间隔；第二个帧跨越对 present 调用后的第一个 Direct3D 和对 `EndCapture` 调用之间的时间间隔。  
  
 若要捕获时间间隔，你必须准备你的应用以捕获并记录图形信息 — 也就是说，你必须已调用[Init](init.md)的实例通过`VsgDbg`类你在调用之前`BeginCapture`或`EndCapture`。  
  
## <a name="see-also"></a>请参阅  
 [BeginCapture](begincapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)