---
title: ShowWebBrowser 命令 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- view.showwebbrowser
helpviewer_keywords:
- ShowWebBrowser command
- View.ShowWebBrowser command
ms.assetid: c6a4fbd6-8e9d-45cc-8b2f-93990d065e78
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c1fca2c1c1dde167c8028d6ad4d543e108a488b4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54798208"
---
# <a name="showwebbrowser-command"></a>ShowWebBrowser 命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
在集成开发环境 (IDE) 中或 IDE 外部显示在 Web 浏览器窗口中指定的 URL。  
  
## <a name="syntax"></a>语法  
  
```  
View.ShowWebBrowser URL [/new][/ext]  
```  
  
## <a name="arguments"></a>自变量  
 `URL`  
 必需。 网站的 URL（统一资源定位器）。  
  
## <a name="switches"></a>开关  
 /new  
 可选。 指定在 Web 浏览器的新实例中显示页。  
  
 /ext  
 可选。 指定在 IDE 外部的默认 Web 浏览器中显示页。  
  
## <a name="remarks"></a>备注  
 ShowWebBrowser 命令的别名是“导航”或“nav”。  
  
## <a name="example"></a>示例  
 以下示例显示在 IDE 外部的 Web 浏览器中的 MSDN Online 主页。 如果 Web 浏览器的实例已打开，则使用它；否则启动一个新实例。  
  
```  
>View.ShowWebBrowser http://msdn.microsoft.com /ext  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [“命令”窗口](../../ide/reference/command-window.md)   
 [“查找/命令”框](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
