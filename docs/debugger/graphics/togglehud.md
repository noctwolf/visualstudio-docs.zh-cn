---
title: ToggleHUD | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e49066d4625990119159ea72f59a3a3fe59d581c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54953297"
---
# <a name="togglehud"></a>ToggleHUD
切换图形诊断*HUD* （显示） 覆盖打开或关闭。  
  
## <a name="syntax"></a>语法  
  
```C++  
void ToggleHUD();  
```  
  
## <a name="remarks"></a>备注  
 图像诊断 HUD 显示在正在图形诊断下运行的应用的左上角。 它将显示有关应用程序、 图形信息捕获，以及通过调用添加的消息的运行时信息[AddMessage](addmessage.md)成员函数。  
  
 若要切换 HUD，您不必主动捕获图形信息-也就是说，它可以通过的实例切换`VsgDbg`类，但[Init](init.md)成员函数无需首先调用。