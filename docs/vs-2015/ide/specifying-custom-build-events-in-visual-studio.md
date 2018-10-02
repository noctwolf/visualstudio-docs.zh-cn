---
title: 在 Visual Studio 中指定自定义生成事件 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- build events, customizing
ms.assetid: 69e935a5-e208-4bcd-865c-3e5f9b047ca8
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3ef870cb6973ff35d620ff09ac781686a9dca508
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483267"
---
# <a name="specifying-custom-build-events-in-visual-studio"></a>在 Visual Studio 中指定自定义生成事件
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[指定自定义生成事件在 Visual Studio 中](https://docs.microsoft.com/visualstudio/ide/specifying-custom-build-events-in-visual-studio)。  
  
通过指定自定义生成事件，可以在生成开始之前或在它完成之后自动运行命令。 例如，可以在生成开始之前运行 .bat 文件，或是在生成完成之后将新文件复制到文件夹中。 仅当生成在生成过程中成功到达这些点时，生成事件才会运行。  
  
 有关所使用的编程语言的特定信息，请参阅以下主题：  
  
-   Visual Basic--[如何：指定生成事件 (Visual Basic)](../ide/how-to-specify-build-events-visual-basic.md)。  
  
-   Visual C# 和 F#--[如何：指定生成事件 (C#)](../ide/how-to-specify-build-events-csharp.md)。  
  
-   Visual C++--[指定生成事件](http://msdn.microsoft.com/library/788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc)。  
  
## <a name="syntax"></a>语法  
 生成事件遵循与 DOS 命令相同的语法，但可以使用宏更轻松地创建生成事件。 有关可用宏的列表，请参阅[预生成事件/生成后事件命令行对话框](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)。  
  
 为获得最佳结果，请遵循以下这些格式设置提示：  
  
-   在运行 .bat 文件的所有生成事件之前添加 `call` 语句。  
  
     示例：`call C:\MyFile.bat`  
  
     示例：`call C:\MyFile.bat call C:\MyFile2.bat`  
  
-   将文件路径用引号引起来。  
  
     示例（对于 [!INCLUDE[win8](../includes/win8-md.md)]）："%ProgramFiles(x86)%\Microsoft SDKs\Windows\v8.0A\Bin\NETFX 4.0 Tools\gacutil.exe" -if "$(TargetPath)"  
  
-   使用换行符分隔多个命令。  
  
-   根据需要包含通配符。  
  
     示例：`for %I in (*.txt *.doc *.html) do copy %I c:\`*mydirectory*`\`  
  
    > [!NOTE]
    >  以上代码中的 `%I` 在批处理脚本中应是 `%%I`。  
  
## <a name="see-also"></a>请参阅  
 [编译和生成](../ide/compiling-and-building-in-visual-studio.md)   
 [预生成事件/生成后事件命令行对话框](../ide/reference/pre-build-event-post-build-event-command-line-dialog-box.md)   
 [MSBuild 特殊字符](../msbuild/msbuild-special-characters.md)   
 [演练：生成应用程序](../ide/walkthrough-building-an-application.md)



