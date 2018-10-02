---
title: Dia2dump 示例 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sample applications [DIA SDK]
- Dia2dump sample [DIA SDK]
ms.assetid: 492c0893-7043-452f-a020-890a47230d20
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 410d4e8cf2a63c7d01058e501391f02543b1eee7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480332"
---
# <a name="dia2dump-sample"></a>Dia2dump 示例
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[Dia2dump 示例](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/dia2dump-sample)。  
  
Dia2dump 示例随 Visual Studio 安装，并包含 Dia2dump.cpp 源文件。 已编译可执行文件从命令行运行，并显示整个程序数据库 (.pdb) 文件的内容。  
  
### <a name="to-install-the-sample"></a>若要安装示例  
  
1.  验证您的系统满足所有 Visual Studio 安装程序起始页中所述的安装程序要求。  
  
2.  安装 Visual Studio，并按照包括的示例的所有设置和安装说明进行都操作。  
  
#### <a name="to-build-the-sample"></a>生成示例  
  
1.  在 Visual Studio 中打开 Dia2dump.sln 文件。 (如有必要，Visual Studio 将首先帮助您升级 Dia2dump 项目。）  
  
2.  在项目属性页中**C/c + +** &#124; **常规** &#124; **附加包含目录**属性，指定`..\DIA SDK\include`目录。 这可确保编译器可以找到 dia2.h 文件。  
  
3.  上**构建**菜单上，单击**重新生成解决方案**。  
  
4.  关闭 Visual Studio。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  打开命令提示符并键入以下命令：  
  
    ```  
    dia2dump filename  
    ```  
  
## <a name="see-also"></a>请参阅  
 [Dia2dump.cpp 源文件](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)   
 [如何：升级 Visual Studio 项目失败疑难解答](../../porting/how-to-troubleshoot-unsuccessful-visual-studio-project-upgrades.md)



