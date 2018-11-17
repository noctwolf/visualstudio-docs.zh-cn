---
title: 调试通用属性解决方案属性页源对话框 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.options.FindSource
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- SQL
- VB
- CSharp
- C++
helpviewer_keywords:
- Debug Source Files property page
- debugging [Visual Studio], specifying source and symbol files
- source files, specifying in debugger
- debugger, source files
ms.assetid: 0af11464-eeb1-4d0b-87a6-0cc96779afb1
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 84bf975065d73cd2d25994855a4c8a236f706e3b
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51744671"
---
# <a name="debug-source-files-common-properties-solution-property-pages-dialog-box"></a>“解决方案属性页”对话框 ->“通用属性”->“调试源文件”
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

该属性页指定调试解决方案时调试器查找源文件的位置。  
  
 访问**调试源文件**属性页中，右键单击你的解决方案中**解决方案资源管理器**，然后选择**属性**从快捷菜单。 展开**常见属性**文件夹，然后单击**调试源文件**页。  
  
 **包含源代码的目录**  
 包含在调试解决方案时调试器搜索源文件的目录的列表。 还可搜索指定目录的子目录。  
  
 **不查找这些源文件**  
 输入不希望调试器读取的任何文件的名称。 如果调试器在以上指定的某个目录中找到这些文件之一，它将忽略该文件。 如果**查找源**时进行调试，并单击对话框中出现**取消**，要搜索的文件添加到此列表，以便调试器不会继续搜索该文件。  
  
## <a name="see-also"></a>请参阅  
 [调试器安全](../debugger/debugger-security.md)   
 [调试器设置和准备](../debugger/debugger-settings-and-preparation.md)



