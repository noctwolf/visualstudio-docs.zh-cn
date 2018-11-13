---
title: 从服务器资源管理器访问 Azure 虚拟机 |Microsoft Docs
description: 获取概述了如何查看创建和管理 Visual Studio 中的服务器资源管理器中的 Azure 虚拟机 (Vm)。
author: ghogen
manager: douge
assetId: eb3afde6-ba90-4308-9ac1-3cc29da4ede0
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 8/31/2017
ms.author: ghogen
ms.openlocfilehash: e1410b3dc60ec9689b6582e794aaf10cd13092aa
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001270"
---
# <a name="accessing-azure-virtual-machines-from-server-explorer"></a>从服务器资源管理器访问 Azure 虚拟机

如果你有托管的 Azure 虚拟机，您可以在服务器资源管理器中访问它们。 您必须首先登录到 Azure 订阅以查看你的移动服务。 若要登录，请在服务器资源管理器中打开 Azure 节点的快捷菜单，然后选择**连接到 Microsoft Azure**。

1. 在云资源管理器，选择虚拟机，并选择 F4 键显示其属性窗口。

    下表显示了哪些属性是可用的但它们是只读的。 若要更改它们，请使用[Azure 门户](http://go.microsoft.com/fwlink/p/?LinkID=525040)。

   | 属性 | 描述 |
   | --- | --- |
   | DNS 名称 |包含虚拟机的 Internet 地址的 URL。 |
   | 环境 |对于虚拟机，此属性的值始终为生产环境。 |
   | name |虚拟机的名称。 |
   | 大小 |虚拟机，这反映了可用的内存和磁盘空间量的大小。 有关详细信息，请参阅[虚拟机大小](https://docs.microsoft.com/azure/cloud-services/cloud-services-sizes-specs)。 |
   | 状态 |值包括正在启动、 启动、 停止、 已停止，且正在检索状态。 如果正在检索状态显示，当前状态是未知的。 此属性的值不同于使用的值[Azure 门户](http://go.microsoft.com/fwlink/p/?LinkID=525040)。 |
   | 订阅 Id |你的 Azure 帐户订阅 ID。 可以显示此信息[Azure 门户](http://go.microsoft.com/fwlink/p/?LinkID=525040)通过查看订阅的属性。 |
2. 选择一个终结点节点，然后查看**属性**窗口。
3. 下表描述了可用属性的终结点，但它们是只读的。 若要添加或编辑虚拟机的终结点，请使用[Azure 门户](http://go.microsoft.com/fwlink/p/?LinkID=525040)。 

   | 属性 | 描述 |
   | --- | --- |
   | name |终结点的标识符。 |
   | 专用端口 |网络访问你的应用程序的内部的端口。 |
   | 协议 |此终结点的传输层使用协议，TCP 或 UDP。 |
   | 公用端口 |用于对你的应用程序的公共访问的端口。 |
