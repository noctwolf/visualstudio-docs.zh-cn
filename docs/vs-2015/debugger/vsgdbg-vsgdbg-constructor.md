---
title: 'Vsgdbg:: Vsgdbg （构造函数） |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 670651e6-5e79-4845-b0c2-671beb7055a8
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f2a35443dbf4fc413908c61e989d2138122c0991
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478632"
---
# <a name="vsgdbgvsgdbg-constructor"></a>VsgDbg::VsgDbg（构造函数）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[vsgdbg:: Vsgdbg （构造函数）](https://docs.microsoft.com/visualstudio/debugger/graphics/vsgdbg-vsgdbg-constructor)。  
  
构造 `VsgDbg` 类的实例（准备或不准备图形诊断的应用内组件）来根据指定的布尔型参数主动捕获并记录图形信息（默认情况下）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
VsgDbg(  
  bDefaultInit  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bDefaultInit`  
 如果指定图形诊断的应用内组件准备主动捕获并记录图形信息，则为 `true`；如果指定应用此时不应准备主动捕获并记录图形信息，则为 `false`。  
  
## <a name="remarks"></a>备注  
 当与调用的构造函数`bDefaultInit`设置为`true`，图形日志文件的文件名由如何`DONT_SAVE_VSGLOG_TO_TEMP`和`VSG_DEFAULT_RUN_FILENAME`预处理器符号定义之前`vsgcapture.h`包含应用程序中。  
  
 如果在 `bDefaultInit` 设置为 `false` 的情况下调用构造函数，则图形诊断的应用内组件可准备以通过调用 `Init` 函数主动捕获图形信息并在稍后记录该信息。  
  
## <a name="see-also"></a>请参阅  
 [VsgDbg:: ~ VsgDbg （析构函数）](../debugger/vsgdbg-tilde-vsgdbg-destructor.md)   
 [Init](../debugger/init.md)   
 [DONT_SAVE_VSGLOG_TO_TEMP](../debugger/dont-save-vsglog-to-temp.md)   
 [VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)


