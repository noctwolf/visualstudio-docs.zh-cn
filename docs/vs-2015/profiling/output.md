---
title: Output | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e286e61-4548-42cf-a635-e608c5edbe2b
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1197d0ee679ea69abb38d789153a57f0e26c3156
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51731057"
---
# <a name="output"></a>输出
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

“Output”选项指定用于性能会话的分析数据文件的名称。 “Output”必须与“Start”选项配合使用。  
  
## <a name="syntax"></a>语法  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>参数  
 `FileName`  
 数据文件的名称。 接受完整和部分路径。 如果未指定路径，则在当前目录中创建该文件。  
  
## <a name="required-options"></a>必需选项  
 “Output”选项必须与“Start”选项一起使用。  
  
 **Start:** `Method`  
 指定输出文件名。  
  
## <a name="example"></a>示例  
 在下例中，分析数据文件是在当前目录中创建的。  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
```  
  
## <a name="see-also"></a>请参阅  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [分析独立应用程序](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [分析 ASP.NET Web 应用程序](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [分析服务](../profiling/command-line-profiling-of-services.md)



