---
title: AddMessage |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de3460a345dba21e3a8f481adb510b9e3bdd4990
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31473343"
---
# <a name="addmessage"></a>AddMessage
将自定义消息添加到图形诊断*HUD* （提醒显示）。  
  
## <a name="syntax"></a>语法  
  
```C++  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szMessage`  
 要添加到 HUD 的消息。  
  
## <a name="remarks"></a>备注  
 图像诊断 HUD 显示在正在图形诊断下运行的应用的左上角。 它显示有关此应用和图形信息捕获的信息以及通过调用此函数添加的消息。  
  
 若要添加到 HUD 的消息，你不必主动捕获图形信息 — 也就是说，可以通过实例添加一条消息`VsgDbg`类，但[Init](init.md)成员函数执行无法首先调用。 消息只显示在 HUD 中，而不会记录在图形日志文件中。