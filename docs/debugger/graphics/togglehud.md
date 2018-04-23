---
title: ToggleHUD |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7261e01d-3c72-46ce-9fb3-5f33b2ddb901
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 86ce582ab49d4d079f01f7231f49aa761baa1069
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="togglehud"></a>ToggleHUD
切换图形诊断*HUD* （提醒显示） 覆盖打开或关闭。  
  
## <a name="syntax"></a>语法  
  
```C++  
void ToggleHUD();  
```  
  
## <a name="remarks"></a>备注  
 图像诊断 HUD 显示在正在图形诊断下运行的应用的左上角。 它显示有关应用和图形信息捕获，并通过调用添加的消息的运行时信息[AddMessage](addmessage.md)成员函数。  
  
 若要切换 HUD，你不必主动捕获图形信息-即，可通过的实例切换`VsgDbg`类，但[Init](init.md)不必首先调用成员函数。