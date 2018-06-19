---
title: 如何：添加、更新或移除 WCF 数据服务引用
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- service references [Visual Studio]
- WCF Data Service reference
- WCF data service references
- ADO.NET service references
- ADO.NET Data Service reference
ms.assetid: 892ebf37-3af4-472e-8744-92837677d611
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 9e39b28a3de5aa97ac7c0673cd16b71508ae4276
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31925971"
---
# <a name="how-to-add-update-or-remove-a-wcf-data-service-reference"></a>如何：添加、更新或移除 WCF 数据服务引用
A*服务参考*，项目可访问一个或多个[!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]。 使用**添加服务引用**对话框中，搜索[!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]当前解决方案中、 本地、 在局域网或 Internet 上。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="adding-a-service-reference"></a>添加服务引用

#### <a name="to-add-a-reference-to-an-external-service"></a>若要添加对外部服务的引用

1.  在**解决方案资源管理器**，右键单击你想要添加到服务，然后单击该项目的名称**添加服务引用**。

     **添加服务引用**对话框随即出现。

2.  在**地址**框中，输入该服务的 URL，然后单击**转**搜索服务。 如果该服务实现用户名称和密码安全性，你可能会提示输入用户名和密码。

    > [!NOTE]
    >  应仅从受信任源引用服务。 从不受信任的源添加引用可能会危及安全性。

     你还可以选择从 URL**地址**列表中，它存储在其中找到了有效的服务元数据前 15 个。

     正在执行搜索时，将显示一个进度栏。 你可以通过单击停止在任何时候搜索**停止**。

3.  在**服务**列表中，展开你想要使用，然后选择一个实体集的服务的节点。

4.  在**Namespace**框中，输入你想要用于参考的命名空间。

5.  单击**确定**添加到项目引用。

     生成服务客户端 （代理），并描述的服务的元数据添加到 app.config 文件。

#### <a name="to-add-a-reference-to-a-service-in-the-current-solution"></a>若要在当前解决方案中添加对服务的引用

1.  在**解决方案资源管理器**，右键单击你想要添加到服务，然后单击该项目的名称**添加服务引用**。

     **添加服务引用**对话框随即出现。

2.  单击**发现**。

     所有服务 (同时[!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]和 WCF 服务) 当前解决方案中添加到**服务**列表。

3.  在**服务**列表中，展开你想要使用，然后选择一个实体集的服务的节点。

4.  在**Namespace**框中，输入你想要用于参考的命名空间。

5.  单击**确定**添加到项目引用。

     生成服务客户端 （代理），并描述的服务的元数据添加到 app.config 文件。

## <a name="updating-a-service-reference"></a>更新服务引用
 用于实体数据模型[!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]有时会发生更改。 在此情况下，必须更新服务引用。

#### <a name="to-update-a-service-reference"></a>若要更新的服务引用

-   在**解决方案资源管理器**，右击该服务引用，然后单击**更新服务引用**。

     从其原始位置，更新的引用和服务客户端会重新生成，以反映的元数据中的任何更改时，将显示进度对话框。

## <a name="removing-a-service-reference"></a>移除服务引用
 如果不再使用的服务引用，你可以从你的解决方案来删除它。

#### <a name="to-remove-a-service-reference"></a>若要删除的服务引用

-   在**解决方案资源管理器**，右击该服务引用，然后单击**删除**。

     服务客户端将删除从解决方案中，并且描述服务的元数据将从 app.config 文件中删除。

    > [!NOTE]
    >  引用的服务引用的任何代码将需要手动删除。

## <a name="see-also"></a>请参阅

- [Visual Studio 中的 Windows Communication Foundation 服务和 WCF 数据服务](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)