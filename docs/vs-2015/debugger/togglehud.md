---
title: ToggleHUD |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b224fdbd4dfadc6af29a0491bba5a18089c260b4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471598"
---
# <a name="togglehud"></a>ToggleHUD
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[ToggleHUD](https://docs.microsoft.com/visualstudio/debugger/graphics/togglehud)。  
  
切换图形诊断*HUD* （显示） 覆盖打开或关闭。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void ToggleHUD();  
```  
  
## <a name="remarks"></a>备注  
 图像诊断 HUD 显示在正在图形诊断下运行的应用的左上角。 它将显示有关应用程序、 图形信息捕获，以及通过调用添加的消息的运行时信息[AddMessage](../debugger/addmessage.md)成员函数。  
  
 若要切换 HUD，您不必主动捕获图形信息-也就是说，它可以通过的实例切换`VsgDbg`类，但[Init](../debugger/init.md)成员函数无需首先调用。



