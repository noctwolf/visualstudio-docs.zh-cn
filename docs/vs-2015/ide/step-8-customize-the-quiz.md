---
title: 步骤 8：自定义测验 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 72e630a3d065e196d33919045316fad27c912750
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483172"
---
# <a name="step-8-customize-the-quiz"></a>第 8 步：自定义测验
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[步骤 8： 自定义测验](https://docs.microsoft.com/visualstudio/ide/step-8-customize-the-quiz)。  
  
在本教程的最后一部分中，您将了解一些自定义测验和扩展所学内容的方式。 例如，可考虑程序如何创建一个答案永不为分数的随机除法问题。 若要了解详细信息，请将 `timeLabel` 控件更改为其他颜色，并为测验者提供提示。  
  
### <a name="to-customize-the-quiz"></a>自定义测验  
  
-   通过设置“timeLabel”控件的“BackColor”属性 (`timeLabel.BackColor = Color.Red;`)，使其在测验只剩下 5 秒时变为红色。 当测验结束时重置颜色。  
  
-   当测验参加者在 NumericUpDown 控件中输入正确答案时，通过播放声音来进行提示。 （您必须为每个控件的 `ValueChanged()` 事件编写事件处理程序，只要用户更改控件的值，就激发该事件。）  
  
### <a name="to-continue-or-review"></a>继续或查看  
  
-   若要下载测验的完整版本，请参阅 [Complete Math Quiz tutorial sample](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c)（数学测验教程的完整示例）。  
  
-   若要转到下一教程，请参阅[教程 3：创建匹配游戏](../ide/tutorial-3-create-a-matching-game.md)。  
  
-   若要返回上一个教程，请参阅[步骤 7：添加乘法和除法问题](../ide/step-7-add-multiplication-and-division-problems.md)。



