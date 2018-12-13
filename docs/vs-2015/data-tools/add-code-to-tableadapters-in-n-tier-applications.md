---
title: N 层应用程序中将代码添加到 Tableadapter |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- TableAdapters, n-tier applications
- n-tier applications, extending TableAdapters
ms.assetid: dafac00e-df9d-4d4a-95a6-e34b4d099425
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 2b5302790d694c23da9e5385adf43c185dc66583
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49207670"
---
# <a name="add-code-to-tableadapters-in-n-tier-applications"></a>向 n 层应用程序中的 TableAdapter 添加代码
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
您可以扩展的功能`TableAdapter`通过创建为分部类文件`TableAdapter`并向其中添加代码 (而不是将代码添加到*DatasetName*。DataSet.Designer 文件）。 分部类启用划分到多个物理文件的特定类代码。 有关详细信息，请参阅[分部](http://msdn.microsoft.com/library/7adaef80-f435-46e1-970a-269fff63b448)或[分部 （类型）](http://msdn.microsoft.com/library/27320743-a22e-4c7b-b0b3-53afe3607334)。  
  
 定义的代码`TableAdapter`每次更改生成`TableAdapter`(在[创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md))。 此代码也会生成任何修改的配置的向导运行期间发生更改时`TableAdapter`。 若要防止你的代码在的重新生成过程中删除`TableAdapter`，将代码添加到分部类文件的`TableAdapter`。  
  
 默认情况下之后将数据集, 和`TableAdapter`代码，结果是每个项目中的离散类文件。 原始项目将包含名为的文件*DatasetName*。Designer.vb (或*DatasetName*。Designer.cs)，其中包含`TableAdapter`代码。 中指定的项目**数据集项目**属性具有名为的文件*DatasetName*。DataSet.Designer.vb (或*DatasetName*。DataSet.Designer.cs)，其中包含数据集代码。  
  
> [!NOTE]
>  分离数据集时， `TableAdapter`s (通过设置**数据集项目**属性)，将不会自动移动项目中的现有数据集分部类。 向数据集项目，必须手动移动现有数据集分部类。  
  
> [!NOTE]
>  [创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)提供用于生成功能<xref:System.Data.DataTable.ColumnChanging>和<xref:System.Data.DataTable.RowChanging>事件处理程序时需要验证。 有关详细信息，请参阅[向 n 层数据集添加验证](../data-tools/add-validation-to-an-n-tier-dataset.md)。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-add-user-code-to-a-tableadapter-in-an-n-tier-application"></a>若要将用户代码添加到 TableAdapter 中的 n 层应用程序  
  
1.  找到包含.xsd 文件的项目 ([创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md))。  
  
2.  双击 **.xsd**文件以打开[创建和编辑类型化数据集](../data-tools/creating-and-editing-typed-datasets.md)。  
  
3.  右键单击`TableAdapter`想要将代码添加到，，然后选择**查看代码**。  
  
     分部类将创建并在代码编辑器中打开。  
  
4.  添加代码的分部类声明。  
  
5.  下面的示例显示了将代码添加到的位置`CustomersTableAdapter`在`NorthwindDataSet`:  
  
    ```vb  
    Partial Public Class CustomersTableAdapter  
        ' Add code here to add functionality   
        ' to the CustomersTableAdapter.  
    End Class  
    ```  
  
    ```csharp  
    public partial class CustomersTableAdapter  
    {  
        // Add code here to add functionality  
        // to the CustomersTableAdapter.  
    }  
    ```  
  
## <a name="see-also"></a>请参阅  
 [N 层数据应用程序概述](../data-tools/n-tier-data-applications-overview.md)   
 [将代码添加到 n 层应用程序中的数据集](../data-tools/add-code-to-datasets-in-n-tier-applications.md)   
 [Tableadapter](http://msdn.microsoft.com/library/09416de9-134c-4dc7-8262-6c8d81e3f364)   
 [TableAdapterManager 概述](http://msdn.microsoft.com/library/33076d42-6b41-491a-ac11-6c6339aea650)   
 [分层更新概述](http://msdn.microsoft.com/library/c4f8e8b9-e4a5-4a02-8462-d03d1e8222d6)   
 [创建数据应用程序](../data-tools/creating-data-applications.md)

