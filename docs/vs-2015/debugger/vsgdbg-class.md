---
title: VsgDbg 类 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6722263c-ccef-40c7-a0ae-87a863fbab00
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 927990cb8fb21dfeaf25a681cfb0a222ecc3c8ed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468628"
---
# <a name="vsgdbg-class"></a>VsgDbg 类
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[VsgDbg 类](https://docs.microsoft.com/visualstudio/debugger/graphics/vsgdbg-class)。  
  
表示用于以编程方式控制图形诊断的应用内组件的接口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
class VsgDbg;  
```  
  
## <a name="members"></a>成员  
 `VsgDbg`类支持以下成员。  
  
### <a name="public-constructors"></a>公共构造函数  
  
|名称|描述|  
|----------|-----------------|  
|[VsgDbg::VsgDbg（构造函数）](../debugger/vsgdbg-vsgdbg-constructor.md)|构造一个实例`VsgDbg`类，并根据需要准备图形诊断来主动捕获并记录图形信息的应用内组件。|  
|[VsgDbg::~VsgDbg（析构函数）](../debugger/vsgdbg-tilde-vsgdbg-destructor.md)|销毁实例`VsgDbg`类。|  
  
### <a name="public-methods"></a>公共方法  
  
|名称|描述|  
|----------|-----------------|  
|[AddMessage](../debugger/addmessage.md)|将自定义消息添加到图形诊断 HUD （显示）。|  
|[BeginCapture](../debugger/begincapture.md)|开始将结尾的捕获时间间隔`EndCapture`。|  
|[CaptureCurrentFrame](../debugger/capturecurrentframe.md)|将当前帧的剩余部分捕获到图形日志文件。|  
|[复制（编程捕获）](../debugger/copy-programmatic-capture.md)|将活动图形日志 (.vsglog) 文件的内容复制到新文件。|  
|[EndCapture](../debugger/endcapture.md)|结束以 `BeginCapture` 开始的捕获时间间隔。|  
|[Init](../debugger/init.md)|准备图形诊断来主动捕获并记录图形信息的应用内组件。|  
|[ToggleHUD](../debugger/togglehud.md)|打开或关闭切换图形诊断 HUD 覆盖。|  
|[UnInit](../debugger/uninit.md)|完成图形日志文件，将其关闭，并且在应用主动记录图形信息时释放已使用的资源。|  
  
## <a name="remarks"></a>备注  
 `VsgDbg`类表示可用于以编程方式控制图形诊断功能的接口。 可以使用一些功能，即使在未主动捕获并记录图形信息;这包括`AddMessage`成员函数和`ToggleHUD`成员函数。 其他成员函数准备图形诊断工具启动或停止活动捕获图形信息的应用内组件，或当应用主动捕获并记录到图形日志文件的图形信息时，必须调用。



