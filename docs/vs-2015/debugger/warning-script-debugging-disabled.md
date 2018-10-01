---
title: 警告： 脚本调试已禁用 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.scriptdisabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 323d2b1d-52a4-42f7-b4ad-96b4b0c23b8d
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 91b54b3e9a70284dc1efb03be7adfaa5d1421920
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471209"
---
# <a name="warning-script-debugging-disabled"></a>警告：脚本调试已禁用
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[警告： 脚本调试被禁用](https://docs.microsoft.com/visualstudio/debugger/warning-script-debugging-disabled)。  
  
脚本调试当前在 Internet Explorer 中禁用  
  
 尝试在未在 Internet Explorer 中启用脚本调试的情况下调试脚本时，会出现此警告。 出于安全考虑，默认情况下，Internet Explorer 禁用脚本调试。  
  
### <a name="to-enable-script-debugging-in-internet-explorer"></a>在 Internet Explorer 中启用脚本调试  
  
1.  Internet explorer**工具**菜单中，选择**Internet 选项**。  
  
2.  在“Internet 选项”  对话框中，单击“高级”  选项卡。  
  
3.  上**高级**选项卡上，查看**设置**框中，**浏览**类别。  
  
4.  清除**禁用脚本调试 (Internet Explorer)**。  
  
5.  单击 **“确定”**。  
  
6.  退出并重新启动 Internet Explorer。  
  
     新设置现在将生效。  
  
## <a name="see-also"></a>请参阅  
 [如何：附加到脚本](../debugger/how-to-attach-to-script.md)



