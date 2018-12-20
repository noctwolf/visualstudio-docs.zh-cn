---
title: Azure SDK for Python
description: Azure SDK for Python 使得从运行在任何平台上的 Python 应用程序中使用 Microsoft Azure 服务更加方便。
ms.date: 12/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: b9c8f5193e55d86ea4ff5e4d68fb7a66a1044d2e
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53062879"
---
# <a name="consume-azure-services-using-the-azure-sdk-for-python"></a>通过 Azure SDK for Python 来使用 Azure 服务

借助 Azure SDK for Python，可以在 Windows、MacOS 和 Linux 上运行的应用程序中轻松使用和管理 Microsoft Azure 服务。

## <a name="installation"></a>安装

从 [Python 包索引](https://pypi.python.org/pypi/azure)安装 Azure SDK。

安装最新稳定版本（支持 Python 2.7 和 3.x），如下所示：

```command
pip install azure
```

还可按照 Azure 文档中的[安装 Python 和 SDK](https://docs.microsoft.com/azure/python-how-to-install/) 操作。

## <a name="documentation"></a>文档

[Azure SDK for Python 开发人员中心](https://docs.microsoft.com/python/azure/?view=azure-python)也有大量有用资源，其中包括许多教程：

- [在 Linux 上的 Azure 应用服务上创建 Web 应用](/azure/app-service/containers/quickstart-python)。
- [Blob 存储](/azure/storage/blobs/storage-quickstart-blobs-python)
- [表存储](/azure/cosmos-db/table-storage-how-to-use-python)
- [队列存储](/azure/storage/storage-python-how-to-use-queue-storage)
- [Azure Cosmos DB](/azure/cosmos-db/sql-api-python-application)
- [服务总线队列](/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
- [服务总线主题/订阅](/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
- [服务管理](/azure/cloud-services/cloud-services-python-how-to-use-service-management)

对于不使用文档的公共 API，[SDK GitHub 存储库](https://github.com/Azure/azure-sdk-for-python)中的单元测试是很好的信息来源：

- [存储单元测试](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [服务总线单元测试](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [服务管理单元测试](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)

## <a name="support"></a>支持

SDK 的 GitHub 存储库位于 [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python)。

如果发现任何问题或对 SDK 用法有任何疑问，请[在存储库中提出问题](https://github.com/Azure/azure-sdk-for-python/issues)。
