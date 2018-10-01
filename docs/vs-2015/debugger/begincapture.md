---
title: BeginCapture |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9edbb52d-ee0b-4cc4-a382-972bcee067d3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2f9bc573799ddb5fdd094c7c0e571a88c13b5420
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469957"
---
# <a name="begincapture"></a>BeginCapture
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[BeginCapture](https://docs.microsoft.com/visualstudio/debugger/graphics/begincapture)。  
  
开始将结尾的捕获时间间隔`EndCapture`。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void BeginCapture();  
```  
  
## <a name="remarks"></a>备注  
 捕获时间间隔通常跨越一个帧的子集，例如，当您仅需要捕获有关某种绘图调用的图形信息时。 如果捕获时间间隔跨越对 present 的调用，则将捕获图形信息的两个帧。 第一个帧跨越对 `BeginCapture` 的调用与对 present 的调用之间的时间间隔；第二个帧跨越对 present 调用后的第一个 Direct3D 和对 `EndCapture` 调用之间的时间间隔。  
  
 若要捕获时间间隔，您必须准备应用以捕获并记录图形信息-也就是说，您必须已调用[Init](../debugger/init.md)的实例通过`VsgDbg`类，然后调用`BeginCapture`或`EndCapture`。  
  
## <a name="see-also"></a>请参阅  
 [EndCapture](../debugger/endcapture.md)   
 [CaptureCurrentFrame](../debugger/capturecurrentframe.md)



