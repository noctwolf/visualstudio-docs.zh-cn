---
title: Visual Basic 特定的 IntelliSense | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IntelliSense [Visual Basic]
- IntelliSense [Visual Studio], Visual Basic
ms.assetid: 4dec8753-05e5-4f74-b304-5f8c4ed8723b
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d9d9d41b6b98396d253b810fb8ea9485a3d9e0df
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49239481"
---
# <a name="visual-basic-specific-intellisense"></a>Visual Basic 特定的 IntelliSense
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Basic 源代码编辑器提供以下 IntelliSense 功能：  
  
-   语法提示  
  
     语法提示显示正在键入的语句的语法。 这对语句而言是有用的，如 [Declare](http://msdn.microsoft.com/library/d3f21fb0-b804-4c99-97ed-583b23894cf1)。  
  
## <a name="automatic-completion"></a>自动完成  
  
-   完成各种关键字  
  
     例如，如果键入 `goto` 和一个空格，IntelliSense 会在下拉菜单中显示已定义的标签列表。 支持的其他关键字包括 `Exit`、`Implements`、`Option` 和 `Declare`。  
  
-   完成 `Enum` 和 `Boolean`  
  
     语句引用枚举成员时，IntelliSense 会显示 `Enum` 成员列表。 语句引用 `Boolean` 时，IntelliSense 会显示 true-false下拉菜单。  
  
 可默认关闭完成，方法是在“Visual Basic”文件夹中，从“常规”属性页取消选择“自动列出成员”。  
  
 可通过调用列表成员、完成单词或 Alt+向右键，手动调用完成。 有关详细信息，请参阅[使用 IntelliSense](../ide/using-intellisense.md)。  
  
## <a name="intellisense-in-zone"></a>IntelliSense in Zone  
 IntelliSense in Zone 可在 Visual Basic 开发人员需要通过 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] 部署应用程序并限制为部分信任设置时提供帮助。 此功能：  
  
-   使你可以选择运行应用程序的权限。  
  
-   显示所选区域中在列表成员中可用的 API，并显示需要将其他权限设置为不可用的 API。  
  
 有关详细信息，请参阅 [ClickOnce 应用程序的代码访问安全性](../deployment/code-access-security-for-clickonce-applications.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 IntelliSense](../ide/using-intellisense.md)



