---
title: BeginCapture |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c2fc3dd2d2851df56d3638333a78f4852ad86bef
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53823809"
---
# <a name="begincapture"></a>BeginCapture
开始将结尾的捕获时间间隔`EndCapture`。  
  
## <a name="syntax"></a>语法  
  
```C++  
void BeginCapture();  
```  
  
## <a name="remarks"></a>备注  
 捕获时间间隔通常跨越一个帧的子集，例如，当您仅需要捕获有关某种绘图调用的图形信息时。 如果捕获时间间隔跨越对 present 的调用，则将捕获图形信息的两个帧。 第一个帧跨越对 `BeginCapture` 的调用与对 present 的调用之间的时间间隔；第二个帧跨越对 present 调用后的第一个 Direct3D 和对 `EndCapture` 调用之间的时间间隔。  
  
 若要捕获时间间隔，您必须准备应用以捕获并记录图形信息-也就是说，您必须已调用[Init](init.md)的实例通过`VsgDbg`类，然后调用`BeginCapture`或`EndCapture`。  
  
## <a name="see-also"></a>请参阅  
 [EndCapture](endcapture.md)   
 [CaptureCurrentFrame](capturecurrentframe.md)