---
title: .Ofs 文件中的一个或多个属性对于选定的消息类不可用 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.NewFormRegionWizard.OFSPropertyError
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ac9f5ab05ba6ed858946b5f665d850eea51c230
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>.ofs 文件中的一个或多个属性对于选定的消息类无效
  如果导入在 Outlook 中设计的窗体区域，但是该窗体区域的一个或多个字段与在“新建窗体区域”  向导最后一页上选择的邮件类不兼容，则会出现此错误。  
  
 例如，你可能在“新建窗体区域”  向导最后一页上选择了“任务(IPM.Task)”  。 如果窗体区域包含“办公地址”  字段，则会出现此错误，这是因为任务是没有办公地址的。 因此，“办公地址”字段  与 IPM.Task 邮件类不兼容。  
  
### <a name="to-correct-this-error"></a>更正此错误  
  
-   在“新建窗体区域”  向导最后一页上，选择与窗体区域上的字段兼容的邮件类。  
  
-   在 Outlook 的窗体设计器中，删除与要在“新建窗体区域”  向导最后一页上选择的邮件类不兼容的字段。  
  
## <a name="see-also"></a>请参阅  
 [演练：导入在 Outlook 中设计的窗体区域](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  