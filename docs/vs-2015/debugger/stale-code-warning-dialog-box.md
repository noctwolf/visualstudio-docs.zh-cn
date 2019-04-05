---
title: 过时的代码警告对话框 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.ENC.stalecode
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Stale Code Warning dialog box
- code, stale code warning
- warnings, Stale Code Warning dialog box
- Edit and Continue, stale code
ms.assetid: 594b894c-e652-4e13-a980-9909473d5712
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: adb8bfdf5edb4f6aa04a53f051fafa9ef3793e10
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58937601"
---
# <a name="stale-code-warning-dialog-box"></a>“陈旧代码警告”对话框
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

当“编辑并继续”操作未能立即应用对本机代码所做的更改时，将显示此对话框。 因此，当前堆栈帧中的某些本机代码是过时的、陈旧的。 有关详细信息，请参阅[如何：使用陈旧代码](http://msdn.microsoft.com/c7536e95-66a6-44a0-995d-3fe5035250b4)。  
  
 **不再显示此对话框**  
 如果选中此复选框，则“编辑并继续”以后将在不要求权限的情况下应用代码更改。 可以通过转到“选项”对话框，打开“调试”文件夹，单击“编辑并继续”页，然后选择“就陈旧的代码发出警告”来再次启用此警告。  
  
## <a name="see-also"></a>请参阅  
 [受支持的代码更改 （c + +）](../debugger/supported-code-changes-cpp.md)   
 [“选项”对话框 ->“调试”->“编辑并继续”](http://msdn.microsoft.com/library/009d225f-ef65-463f-a146-e4c518f86103)
