---
title: 如何： 启用复数化打开和关闭 （O-R 设计器） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 02fa8b50b28f967a0835f68e85d146ca1eea514b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47492526"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>如何： 启用复数化打开和关闭 （O/R 设计器）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 打开和关闭 （O-R 设计器） 启用复数化](https://docs.microsoft.com/visualstudio/data-tools/how-to-turn-pluralization-on-and-off-o-r-designer)。  
  
  
默认情况下，当您拖放以 s 或 ies 从结尾的数据库对象**服务器资源管理器**/**数据库资源管理器**拖到[LINQ to SQL 工具在 Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)，生成的实体类的名称从复数形式更改为单数形式。 这样可以更准确地表示实例化的实体类映射到单个数据记录的事实。 例如，将 Customers 表添加到 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]将声称名为 Customer 的实体类，因为该类将仅为一个客户保存数据。  
  
> [!NOTE]
>  默认情况下，复数形式仅在 Visual Studio 的英语版本中启用。  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-turn-pluralization-on-and-off"></a>打开和关闭复数形式  
  
1.  在 **“工具”** 菜单上，单击 **“选项”**。  
  
2.  在中**选项**对话框框中，展开**Database Tools**。  
  
> [!NOTE]
>  选择**显示所有设置**如果**Database Tools**节点不可见。  
  
1.  单击**O/R 设计器**。  
  
2.  设置**名称的复数形式**到**已启用** = **False**设置[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]，以便它不会更改类名称。  
  
3.  设置**名称的复数形式**到**已启用** = **True**若要添加到的对象的类名称应用复数规则[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]。  
  
## <a name="see-also"></a>请参阅  
 [LINQ to SQL 工具在 Visual Studio 中](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [在 Visual Studio 中访问数据](../data-tools/accessing-data-in-visual-studio.md)

