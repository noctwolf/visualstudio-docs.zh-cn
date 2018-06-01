---
title: .ofs 文件中的一个或多个属性对于选定的消息类无效
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
ms.openlocfilehash: cfae8533337bbe18c89dbb670fb58a0c89c6c54c
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692494"
---
# <a name="one-or-more-properties-in-the-ofs-file-are-not-valid-for-the-message-class-selected"></a>.ofs 文件中的一个或多个属性对于选定的消息类无效
  导入在 Outlook 中设计的窗体区域时，会出现此错误，但在窗体区域上的一个或多个字段与不兼容的最后一页选择的邮件类**新窗体区域**向导。  

例如，你可能在“新建窗体区域”  向导最后一页上选择了“任务(IPM.Task)”  。 如果窗体区域具有**业务地址**字段，你将收到此错误，因为任务没有办公地址。 因此，**业务地址**字段不是与兼容`IPM.Task`message 类。  
  
 你可能会选择**任务 (IPM。任务）** 的最后一页上**新窗体区域**向导。 如果窗体区域具有**业务地址**字段，你将收到此错误，因为任务没有办公地址。 因此，**业务地址**字段不是与兼容`IPM.Task`message 类。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   在“新建窗体区域”  向导最后一页上，选择与窗体区域上的字段兼容的邮件类。  
  
-   在 Outlook 中窗体设计器，删除与的邮件类不兼容的字段。 删除计划的最后一页选择的字段**新窗体区域**向导。  
  
## <a name="see-also"></a>请参阅  
 [演练： 导入在 Outlook 中设计的窗体区域](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  