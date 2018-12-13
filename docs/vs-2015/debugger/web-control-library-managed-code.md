---
title: Web 控件库 （托管代码） |Microsoft Docs
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
- debugging DLLs
- debugging [Visual Studio], Web control libraries
ms.assetid: 2413883f-9e88-406d-b874-0ed743b75d40
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a523d593b4c61a7ca730cc60a6ed22a1be541f9c
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51807584"
---
# <a name="web-control-library-managed-code"></a>Web 控件库（托管代码）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Web 控件库项目模板创建 DLL。 因为类库是 DLL，所以不能直接运行它。 必须创建嵌入该控件的 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 页。 有关详细信息，请参阅[Web 控件库模板](http://msdn.microsoft.com/en-us/00666b07-71d2-4ace-a13c-cc130a3ce372)。  
  
### <a name="to-debug-a-web-control-library-method-1"></a>调试 Web 控件库（方法 1）  
  
1.  打开一个现有的 Web 控件库项目，或者新建一个项目。  
  
2.  创建嵌入该控件的 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 页。  
  
3.  在承载 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 测试套的网站上，创建名为 `/Code` 的子目录。  
  
4.  将该控件的源代码复制到 `/Code` 子目录中。  
  
5.  打开 `/Code` 子目录下的源代码并设置断点。  
  
6.  打开浏览器窗口，将 URL 指向该测试套。 控件中的断点将被命中，您可以开始调试。  
  
### <a name="to-debug-a-web-control-library-method-2"></a>若要调试 Web 控件库 (方法 2)  
  
1.  创建宿主应用程序项目，并在同一解决方案中创建 Web 控件项目。  
  
2.  在中**解决方案资源管理器**，右键单击主机应用程序，然后选择**添加引用**。  
  
3.  向该 Web 控件项目添加引用。  
  
## <a name="see-also"></a>请参阅  
 [ASP.NET Web 应用程序](../debugger/debugging-preparation-aspnet-web-applications.md)



