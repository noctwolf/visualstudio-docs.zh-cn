---
title: UnInit |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cd4fc0b-974a-4e61-9ea8-0aaa1a0c52ea
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4cd66d7329fa4bfc288f3d60879e45cc86ded94e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471682"
---
# <a name="uninit"></a>UnInit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[UnInit](https://docs.microsoft.com/visualstudio/debugger/graphics/uninit)。  
  
完成图形日志文件，将其关闭，并且在应用主动记录图形信息时释放已使用的资源。  
  
## <a name="syntax"></a>语法  
  
```cpp  
void UnInit();  
```  
  
## <a name="remarks"></a>备注  
 在销毁 `UnInit` 类的实例后自动调用 `VsgDbg`。 如果 `VsgDbg` 实例未主动记录图形信息，则此操作不起作用。  
  
 在对 `UnInit` 类的实例调用 `VsgDbg` 之后，可通过调用 `Init` 创建新的图形日志文件，并通过调用 `UnInit` 完成此日志文件。 您可以重复此操作所需次数以使用相同的 `VsgDbg` 实例来创建多个独立的图形日志文件。  
  
## <a name="see-also"></a>请参阅  
 [Init](../debugger/init.md)



