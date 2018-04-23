---
title: 如何： 向 Word 文档添加 XMLNodes 控件 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNodes control, adding to documents
- controls [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1ff96af4078883bf77d3632d08b6417ff1c34e2f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-xmlnodes-controls-to-word-documents"></a>如何：向 Word 文档添加 XMLNodes 控件
  **重要**提出有关 Microsoft Word 本主题中的信息不提供的以独占方式适合的好处和使用个人和组织用户位于美国和其区域之外，或使用，或开发在运行的程序，在 2010 年 1 月，Microsoft 中删除的特定功能实现的时间之前已授权的 Microsoft 的 Microsoft Word 产品被与 Microsoft Word 自定义 XML。 有关 Microsoft Word 此信息不能读取或使用的个人或美国或其地区熟悉使用，或开发在 Microsoft Word 2010 年 1 月 10 日之后已授权的 Microsoft 的产品运行的程序中的组织;这些产品将无法与产品许可在该日期之前或购买并获得美国以外的使用许可相同。  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 当你重复的 XML 架构元素映射到 Microsoft Office Word 文档时，Visual Studio 会自动添加<xref:Microsoft.Office.Tools.Word.XMLNodes>到您的文档的控制。  
  
 有关映射非重复的 XML 架构元素的信息，请参阅[如何： 向 Word 文档添加 XMLNode 控件](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)。  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Word.XMLNodes>控件不能从**工具箱**或**数据源**窗口中，也不以编程方式创建。  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-an-xmlnodes-control-to-a-document"></a>若要向文档添加 XMLNodes 控件  
  
1.  在文档中在 Visual Studio 设计器中，在功能区中，单击**开发人员**选项卡。  
  
    > [!NOTE]  
    >  如果看不到 **“开发人员”** 选项卡，则必须首先显示它。 有关详细信息，请参阅 [如何：在功能区上显示“开发人员”选项卡](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)。  
  
2.  在**XML**组中，单击**架构**。  
  
     **模板和外接程序**对话框随即打开。  
  
3.  单击**XML 架构**选项卡。  
  
4.  单击**将架构添加**。  
  
     **添加架构**对话框随即打开。  
  
5.  选择 XML 架构包含重复架构元素和单击**打开**。  
  
     **架构设置**对话框随即出现。  
  
6.  分配一个别名，或单击**确定**以添加别名没有架构。  
  
     该架构添加到**添加架构**对话框。  
  
7.  在**添加架构**对话框中，单击**确定**。  
  
     **XML 结构**任务窗格随即打开。  
  
8.  单击重复架构元素**XML 结构**任务窗格以将其添加到文档。  
  
     <xref:Microsoft.Office.Tools.Word.XMLNodes>创建控件并将其添加到项目。  
  
## <a name="see-also"></a>另请参阅  
 [XMLNodes 控件](../vsto/xmlnodes-control.md)   
 [使用扩展对象实现 Word 自动化](../vsto/automating-word-by-using-extended-objects.md)   
 [宿主项和宿主控件概述](../vsto/host-items-and-host-controls-overview.md)   
 [主机项和主机控件的编程限制](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  