---
title: 用于调试 Azure 云服务 |Microsoft Docs
description: 调试 Azure 云服务
author: mikejo5000
manager: douge
ms.assetid: 80755da7-8350-4f5c-97ce-2962beabb36d
ms.topic: conceptual
ms.workload: azure-vs
ms.date: 03/18/2017
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.openlocfilehash: bd2608371871b7adc925fc11927fe061b00a1ec6
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001557"
---
# <a name="learn-the-various-ways-to-debug-an-azure-cloud-service"></a>了解调试 Azure 云服务的各种方法
本文提供指向调试 Azure 云服务的各种方法。 

## <a name="debugging-an-azure-cloud-service-in-visual-studio"></a>调试 Visual Studio 中的 Azure 云服务
您可以节省时间和资金，通过使用 Azure 计算模拟器调试本地计算机上的云服务。 通过本地调试服务，在部署之前，可以提高可靠性和性能而无需为计算时间付费。 但是，仅当在 Azure 中运行云服务时，可能会发生一些错误。 可以通过启用远程调试，当你发布你的服务时，然后将调试器附加到角色实例来调试在 Azure 中运行云服务时，才会发生的错误。 有关详细信息，请参阅[调试在本地计算机上的云服务](vs-azure-tools-debug-cloud-services-virtual-machines.md#debug-your-cloud-service-on-your-local-computer)。

## <a name="using-intellitrace"></a>使用 IntelliTrace 
如果你使用 Visual Studio Enterprise 来编写角色针对.NET Framework 4.5，则可以在部署 Visual Studio 中的 Azure 云服务时启用 IntelliTrace。 IntelliTrace 提供日志，可以使用 Visual Studio 中使用，若要调试你的应用程序就如同它在 Azure 中运行。 有关详细信息，请参阅[调试已发布的云服务使用 IntelliTrace 和 Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=623016)。

## <a name="remote-debugging"></a>远程调试 
您可以在部署 Visual Studio 中的云服务时的时间在云服务上的远程调试。 如果您选择为部署启用远程调试，运行每个角色实例的虚拟机上安装远程调试服务。 这些服务-如`msvsmon.exe`-不会影响性能或导致额外成本。 有关详细信息，请参阅[调试在 Azure 中的云服务](vs-azure-tools-debug-cloud-services-virtual-machines.md#debug-a-cloud-service-in-azure)。

## <a name="next-steps"></a>后续步骤
- [Visual Studio 中调试 Azure 云服务或 VM](./vs-azure-tools-debug-cloud-services-virtual-machines.md) -了解如何调试 Azure 云服务的详细信息。