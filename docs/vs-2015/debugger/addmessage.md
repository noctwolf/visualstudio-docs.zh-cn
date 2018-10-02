---
title: AddMessage |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 102a0404-a00c-4566-93f3-01bc8df63280
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a81dda4564d87fe33d9d8e9c497e4aa040b8830e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469668"
---
# <a name="addmessage"></a>AddMessage
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[AddMessage](https://docs.microsoft.com/visualstudio/debugger/graphics/addmessage)。  
  
将自定义消息添加到图形诊断*HUD* （显示）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void AddMessage(  
  wchar_t const * szMessage  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szMessage`  
 要添加到 HUD 的消息。  
  
## <a name="remarks"></a>备注  
 图像诊断 HUD 显示在正在图形诊断下运行的应用的左上角。 它显示有关此应用和图形信息捕获的信息以及通过调用此函数添加的消息。  
  
 若要将消息添加到 HUD，您不必主动捕获图形信息-也就是说，通过的实例添加消息`VsgDbg`类，但[Init](../debugger/init.md)成员函数执行的操作不以首先调用。 消息只显示在 HUD 中，而不会记录在图形日志文件中。



