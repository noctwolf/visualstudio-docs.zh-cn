---
title: 调试数据绑定 ActiveX 控件 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- data-bound controls, ActiveX
- ActiveX controls, debugging
- controls [Visual Studio], ActiveX
ms.assetid: 9f6e1f00-e25b-48a9-8484-7e67a1232461
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b993d6a6121c4e7631a51877cbfffa231e0714ea
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49177133"
---
# <a name="debugging-a-data-bound-activex-control"></a>调试数据绑定 ActiveX 控件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

如果开发的是将被绑定到数据源控件的 ActiveX 控件，可以通过创建自己的容器应用程序并将该容器用于调试该 ActiveX 控件。  
  
 例如，创建基于对话的 MFC 应用程序并将数据绑定控件和数据源控件放在该对话框上。 可将该 MFC 应用程序用于运行时测试和用作调试数据绑定 ActiveX 控件的容器可执行文件。  
  
## <a name="using-the-test-container"></a>使用测试容器  
 如果需要可以轻松修改以支持控件或容器上的各种接口的容器，则将 ActiveX 测试容器用作调试会话的可执行文件。 在 ActiveX 测试容器中，单击**选项**从**容器**菜单以启用各种接口。 有关详细信息，请参阅[使用测试容器测试属性和事件](http://msdn.microsoft.com/library/626867cf-fe53-4c30-8973-55bb93ef3917)。  
  
 如果在调试时需要单步执行容器的代码，请使用容器的调试版本或者使用 ActiveX 测试容器的调试版本。 有关详细信息，请参阅[TSTCON 示例： ActiveX 控件测试容器](http://msdn.microsoft.com/en-us/72fa40ef-27d3-400c-813f-10b03236e600)。  
  
## <a name="see-also"></a>请参阅  
 [调试 COM 和 ActiveX](../debugger/com-and-activex-debugging.md)   
 [ActiveX 控件](http://msdn.microsoft.com/library/52aaec4d-3889-402e-b57d-758078f8ac57)



