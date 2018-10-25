---
title: 如何： 禁用 ClickOnce 应用程序的 URL 激活 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- disallowUrlActivation
- URL activation, ClickOnce applications
- ClickOnce deployment, URL activation
ms.assetid: db31a16b-960f-4264-91d7-c7c40f876068
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9ab9204513c59d2c853c0a3738ef2363739d56c1
ms.sourcegitcommit: 551f13774e8bb0eb47cbd973745628a956e866aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2018
ms.locfileid: "49459616"
---
# <a name="how-to-disable-url-activation-of-clickonce-applications"></a>如何： 禁用 ClickOnce 应用程序的 URL 激活

通常，从 Web 服务器安装 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 应用程序后它会立即自动启动。 出于安全原因，您可以决定禁用此行为，并告知用户启动应用程序从**启动**菜单相反。 以下过程描述了如何禁用 URL 激活。

此方法仅适用于从 Web 服务器安装到用户计算机上的 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 应用程序。 它不能用于仅联机应用程序，仅联机应用程序可以通过使用其 URL 启动。 只能联机使用的和已安装的应用程序之间区别的详细信息，请参阅[选择 ClickOnce 部署策略](../deployment/choosing-a-clickonce-deployment-strategy.md)。

此过程使用 Windows 软件开发工具包 (SDK) 工具 MageUI.exe。 此工具的详细信息，请参阅[MageUI.exe (Manifest Generation and Editing Tool，Graphical Client)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)。 此外可以执行此过程使用 Visual Studio。

## <a name="procedure"></a>过程

### <a name="to-disable-url-activation-for-your-application"></a>禁用应用程序的 URL 激活的步骤

1.  在 MageUI.exe 中打开部署清单。 如果尚未创建一个，请按照中的步骤[演练： 手动部署 ClickOnce 应用程序](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)。

2.  选择**部署选项**选项卡。

3.  清除**自动运行安装后的应用程序**复选框。

4.  保存并对清单进行签名。

## <a name="see-also"></a>请参阅

- [发布 ClickOnce 应用程序](../deployment/publishing-clickonce-applications.md)