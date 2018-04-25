---
title: -LCID (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /LCID switch
- locale IDs
- /l Devenv switch
- LCID devenv switch
- /lcid Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0588152e99fd6e81d47df691b4e84535cc7fbe9e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)
设置集成开发环境 (IDE) 内文本、货币和其他值使用的默认语言。  
  
## <a name="syntax"></a>语法  
  
```  
devenv {/LCID|/l} LocaleID  
```  
  
## <a name="arguments"></a>自变量  
 `LocaleID`  
 必须的。 指定的语言的 LCID（区域设置 ID）。  
  
## <a name="remarks"></a>备注  
 加载 IDE 并设置环境的默认自然语言。 此更改保留在会话中，并反映在 IDE 的“选项”对话框中“环境”选项的“国际设置”窗格上。  
  
 如果指定的语言在用户的系统上不可用，则忽略 /LCID 开关。  
  
 下表列出了受 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 支持的语言的 LCID。  
  
|语言|LCID|  
|--------------|----------|  
|中文（简体）|2052|  
|和 SharePoint 2010 显示的“中文(繁体)”|1028|  
|英语|1033|  
|法语|1036|  
|德语|1031|  
|意大利语|1040|  
|日语|1041|  
|朝鲜语|1042|  
|西班牙语|3082|  
  
## <a name="example"></a>示例  
 此示例加载具有英语资源字符串的 IDE。  
  
```  
devenv /LCID 1033  
```  
  
## <a name="see-also"></a>请参阅  
 [Devenv 命令行开关](../../ide/reference/devenv-command-line-switches.md)   
 [“选项”对话框 ->“环境”->“区域设置”](../../ide/reference/international-settings-environment-options-dialog-box.md)   
 [自定义窗口布局](../../ide/customizing-window-layouts-in-visual-studio.md)