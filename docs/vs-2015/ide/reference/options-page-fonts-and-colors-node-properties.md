---
title: “选项”页 ->“字体和颜色”节点属性 | Microsoft Docs
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
- Tools Options settings, Fonts and Colors node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 8e1ab784-5f85-4e2b-8ef9-e5d59ca4dbcb
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 18524cb3b27a05763187b9d5567d127af39c25d3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478581"
---
# <a name="options-page-fonts-and-colors-node-properties"></a>“选项”页 ->“字体和颜色”节点属性
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[选项页、 字体和颜色节点属性](https://docs.microsoft.com/visualstudio/ide/reference/options-page-fonts-and-colors-node-properties)。  
  
  
本文档介绍某个工具窗口的字体和颜色属性，该窗口注册显示在“选项”对话框“环境”类别中的”字体和颜色”下。 这支持可着色项组的动态特性，安装或卸载 VSPackages 时，这些特性可能会发生更改。  
  
 以下部分显示了已注册窗口类型的示例，以及可用于每个窗口的属性。  
  
## <a name="text-editor-or-printer-or-dialogs-and-tool-windows"></a>文本编辑器、打印机或对话框和工具窗口  
 `DTE.Properties("FontsAndColors", "TextEditor")`  
  
 -或-  
  
 `DTE.Properties("FontsAndColors", "Printer")`  
  
 或  
  
 `DTE.Properties("FontsAndColors", "Dialogs and Tool Windows")`  
  
|属性项名称|“值”|描述|  
|------------------------|-----------|-----------------|  
|FontFamily|Get/Set (String)|要使用的字体名称，如“Courier New”。|  
|FontCharacterSet|Get/Set (<xref:EnvDTE.vsFontCharSet>)|<xref:EnvDTE.vsFontCharSet> 值，指定要使用的字符集的类型，例如希伯来语或俄语。|  
|FontSize|Get/Set (Short)|要使用的字体大小（以磅为单位）。 例如，10 或 12。|  
  
## <a name="see-also"></a>请参阅  
 [控制选项设置](http://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [确定“选项”页中属性项的名称](http://msdn.microsoft.com/library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [“选项”页 ->“环境”节点属性](../../ide/reference/options-page-environment-node-properties.md)   
 [“选项”页 ->“文本编辑器”节点属性](../../ide/reference/options-page-text-editor-node-properties.md)



