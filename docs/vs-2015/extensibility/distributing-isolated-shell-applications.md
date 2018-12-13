---
title: 分发独立的 Shell 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c503a985-d67a-4ef8-9123-7744a78f2f17
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 27228131c1e955a394e666ac05f0ddd68c879be0
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51758779"
---
# <a name="distributing-isolated-shell-applications"></a>分发独立的 Shell 应用程序
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

若要创建独立的 shell 应用程序，必须安装 Visual Studio 和 Visual Studio SDK。 若要分发到计算机的其他用户或客户应用程序，必须包括独立 shell 的特殊可再发行组件包。  
  
## <a name="prerequisites-for-distributing-isolated-shell-applications"></a>分发独立的 Shell 应用程序的先决条件  
  
|name|描述|  
|----------|-----------------|  
|Visual Studio SDK|您必须开发和测试的扩展 SDK [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。 SDK 还可用于创建你自己的 Visual Studio 独立 shell 的实例。<br /><br /> Visual Studio 是 SDK 的必备组件。|  
|Microsoft Visual Studio 独立 Shell 可再发行组件|可再发行的生成上 Visual Studio 的工具环境时纳入您的安装程序独立 shell。 独立的 Shell 可再发行组件包包含.NET Framework 4.5。|  
  
## <a name="creating-an-installation-program-for-the-application"></a>为应用程序创建安装程序  
 必须为集成或独立 shell 应用程序创建的特殊安装程序。 有关详细信息，请参阅[安装独立 Shell 应用程序](../extensibility/installing-an-isolated-shell-application.md)。  
  
## <a name="allowing-for-updates-to-your-application"></a>允许你应用程序的更新  
 安装程序必须允许，您的应用程序将更新，Microsoft 更新或你公司的更新的可能性。 有关更新的详细信息，请参阅[维护独立 Shell 应用程序的准则](../extensibility/servicing-guidelines-for-isolated-shell-applications.md)。

