---
title: 如何：显示外接程序用户界面错误
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], user interface errors
- errors [Office development in Visual Studio], user interface errors
- user interfaces [Office development in Visual Studio], errors
- application-level add-ins [Office development in Visual Studio], user interface errors
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 466b316340f922d13ed559791d1340912c4cecfd
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "54862910"
---
# <a name="how-to-show-add-in-user-interface-errors"></a>如何：显示外接程序用户界面错误
  默认情况下，如果 VSTO 外接程序尝试操作 Microsoft Office 用户界面 (UI) 和失败，将不显示任何错误消息。 但是，你可以配置 Microsoft Office 应用程序以显示与 UI 相关的错误的消息。 这些消息可用于帮助确定为何未显示自定义功能区，或者为何功能区出现但控件未出现。  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
## <a name="to-show-vsto-add-in-user-interface-errors"></a>显示 VSTO 外接程序用户界面错误  
  
1.  启动应用程序。  
  
2.  单击 **“文件”** 选项卡。  
  
3.  单击“选项” 。  
  
4.  在类别窗格中，单击“高级” 。  
  
5.  在细节窗格中，选择“显示 VSTO 外接程序用户界面错误” ，然后单击“确定” 。  
  
    > [!NOTE]  
    >  对于 Outlook，“显示 VSTO 外接程序用户界面错误”  复选框位于细节窗格的“开发工具”  部分。 对于其他应用程序，该复选框位于细节窗格的“常规”  部分。  
  
## <a name="see-also"></a>请参阅  
 [Office UI 自定义](../vsto/office-ui-customization.md)   
 [创建 Outlook 窗体区域](../vsto/creating-outlook-form-regions.md)   
 [功能区概述](../vsto/ribbon-overview.md)   
 [操作窗格概述](../vsto/actions-pane-overview.md)  
